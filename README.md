#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <ncurses.h>

int main()
{
    int  choix,choix1,choix2,choix3,quan1,quan2,quan3,i,tour;
    int rst1=5, rst2=5, rst3=6;
    float taxe,somme,total;
    quan1=quan2=quan3=0;

    printf("     Bienvenue a Angi's Meal!!!\n\n");
    printf("           ***MENU***\n\n");
    printf("1- Salade Mediterraneenne- 6.50$ (Stock: 5)\n");
    printf("2- Poulet au Curry Doux- 12.9$ (Stock: 5)\n");
    printf("3- Fondant au chocolat- 5$ (Stock: 6)\n\n Regaler vous!!!\n\n");
    printf("Voulez-vous passer une commande? (Entrez 1 pour dire oui et 0 pour non) :"); scanf("%d",&choix);
    //on applique une taxe de 10%
    taxe=((6.5+12.9+5)*10)/100;

    if(choix==0)
    {
        return 0;
    }


    printf("\nVoulez-vous le plat 1? :"); scanf("%d",&choix1);
    if(choix1==1)
    {
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan1);
        rst1=rst1-quan1;
        while(quan1>5)
        {
            printf("Notre stock c'est 5 et vous demander une mauvaise quantite!!\nRetaper la quantite :");
            scanf("%d",&quan1);
        }
    }
    else
    {
        printf("Il est pourtant bon mais ok.\n");
    }

    printf("\nVoulez-vous le plat 2? :"); scanf("%d",&choix2);
    if(choix2==1)
    {
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan2);
        rst2=rst2-quan2;
        while(quan2>5)
        {
            printf("Notre stock c'est 5 et vous demander une mauvaise quantite!!\nRetaper la quantite :");
            scanf("%d",&quan1);
        }
    }
    else
    {
        printf("Ne ratez pas ce delice mais ok c'est votre choix.\n");
    }

    printf("\nVoulez-vous le plat3? :");  scanf("%d",&choix3);

    if(choix3==1)
    {
        rst3=rst3-quan3;
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan3);
        while(quan3>5)
        {
            printf("Notre stock c'est 5 et vous demander une mauvaise quantite!!\nRetaper la quantite :");
            scanf("%d",&quan1);
        }
    }
    else
    {
        printf("Ok aucun dessert pour cette ravissante personne.\n");
    }


    //Preparation des commandes

    if(choix1==1 || choix2==1 || choix3==1)
    {
                /*Meme en ayant decide de commander leur quantite peuvent etre des quantites nulles dont nos si
                des choix dependront aussi des si des quantites*/

                if(quan1!=0 && quan2!=0 && quan3!=0)
                {
                         printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de salade, %d plats de poulets au curry et %d bols de \nfondant au chocolat.\n\n\n",quan1,quan2,quan3);
                         printf(" _________________________________________________________________________________________________________\n");
                         printf("|                                     **** STATUS D'AVANCEMENT DES PLATS  ****                            |\n");
                         printf("|_________________________________________________________________________________________________________|\n");

                         printf("Plat 1 en attente          |            Plat 2 en attente        |         Plat 3 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"



                        printf("\033[31;18H.");printf("\033[31;59H.");printf("\033[31;95H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");printf("\033[31;60H.");printf("\033[31;96H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");printf("\033[31;61H.");printf("\033[31;97H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 presque pret        |     Plat 2 presque pret             |    Plat 3 pret(Ce dessert est rapide)");
                        printf("\033[32;20H.");printf("\033[32;53H.");fflush(stdout);sleep(4);
                        printf("\033[32;21H.");printf("\033[32;54H.");fflush(stdout);sleep(4);
                        printf("\033[32;22H.");printf("\033[32;55H.");fflush(stdout);sleep(4);


                        printf("\nAttendez encore un peu     |            Plat 2 pret              |     Dessert deja pret!!!");
                        printf("\033[33;24H.");fflush(stdout);sleep(4);
                        printf("\033[33;25H.");fflush(stdout);sleep(4);
                        printf("\033[33;26H.");fflush(stdout);sleep(4);



                        printf("\nPlat 1 pret!!!             |      Plat 2 pret depuis 1 min       |    Plat 3 pret depuis 2 min au moins");


                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n                __________\n                       ");
                         printf("             |   TOTAL  |\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }

                else if(quan1==0 && quan2==0 && quan3==0)
                {
                    printf("\nVous n'avez en realite rien commande.\n, Pas grave, bonne suite a vous ,revenez quand vous voulez.");
                }

                else if(quan1==0 && quan2==0 && quan3!=0)
                {
                    printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d bols de fondant au chocolat.\n\n\n",quan1,quan2,quan3);
                         printf(" _________________________________________________________________________________________________________\n");
                         printf("|                                     **** STATUS D'AVANCEMENT DES PLATS  ****                            |\n");
                         printf("|_________________________________________________________________________________________________________|\n");

                         printf("Plat 3 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"



                        printf("\033[31;18H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");fflush(stdout);sleep(4);

                        printf("\nPlat 3 pret(Ce dessert est rapide)");

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n                __________\n                       ");
                         printf("             |   TOTAL  |\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }

                else if(quan1==0 && quan2!=0 && quan3!=0)
                {
                    printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de poulets au curry et %d bols de \nfondant au chocolat.\n\n\n",quan1,quan2,quan3);
                         printf(" _________________________________________________________________\n");
                         printf("|         **** STATUS D'AVANCEMENT DES PLATS  ****                |\n");
                         printf("|_________________________________________________________________|\n");

                         printf("Plat 2 en attente        |         Plat 3 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"



                        printf("\033[31;18H.");printf("\033[31;59H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");printf("\033[31;60H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");printf("\033[31;61H.");fflush(stdout);sleep(4);

                        printf("\nPlat 2 presque pret      |    Plat 3 pret(Ce dessert est rapide)");
                        printf("\033[32;20H.");fflush(stdout);sleep(4);
                        printf("\033[32;21H.");fflush(stdout);sleep(4);
                        printf("\033[32;22H.");fflush(stdout);sleep(4);


                        printf("\nPlat 2 pret              |     Dessert deja pret!!!");

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n              __________\n                       ");
                         printf("             ****|   TOTAL  |****\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }

                else if(quan1==0 && quan2!=0 && quan3==0)
                {
                         printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de poulets au curry.\n\n\n",quan1,quan2,quan3);
                         printf(" _____________________________________________________\n");
                         printf("|  **** STATUS D'AVANCEMENT DES PLATS  ****           |\n");
                         printf("|_____________________________________________________|\n");

                         printf("Plat 2 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                        printf("\033[31;18H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");fflush(stdout);sleep(4);

                        printf("\nPlat 2 presque pret");
                        printf("\033[32;20H.");fflush(stdout);sleep(4);
                        printf("\033[32;21H.");fflush(stdout);sleep(4);
                        printf("\033[32;22H.");fflush(stdout);sleep(4);

                        printf("\nPlat 2 pret");

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n                __________\n                       ");
                         printf("             ****|   TOTAL  |****\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }

                else if(quan1!=0 && quan2==0 && quan3==0)
                {
                    printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de salade uniquement.\n\n\n",quan1,quan2,quan3);
                         printf(" ______________________________________________________\n");
                         printf("|     **** STATUS D'AVANCEMENT DES PLATS  ****         |\n");
                         printf("|______________________________________________________|\n");

                         printf("Plat 1 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                        printf("\033[31;18H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 presque pret");
                        printf("\033[32;20H.");fflush(stdout);sleep(4);
                        printf("\033[32;21H.");fflush(stdout);sleep(4);
                        printf("\033[32;22H.");fflush(stdout);sleep(4);


                        printf("\nAttendez encore un peu");
                        printf("\033[33;24H.");fflush(stdout);sleep(4);
                        printf("\033[33;25H.");fflush(stdout);sleep(4);
                        printf("\033[33;26H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 pret!!!");

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n                __________\n                       ");
                         printf("             ****|   TOTAL  |****\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }

                else if(quan1!=0 && quan2!=0 && quan3==0)
                {
                    printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de salade et %d plats de poulets au curry.\n\n\n",quan1,quan2,quan3);
                         printf(" _______________________________________________________________\n");
                         printf("|        **** STATUS D'AVANCEMENT DES PLATS  ****               |\n");
                         printf("|_______________________________________________________________|\n");

                         printf("Plat 1 en attente          |            Plat 2 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                        printf("\033[31;18H.");printf("\033[31;59H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");printf("\033[31;60H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");printf("\033[31;61H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 presque pret        |     Plat 2 presque pret");
                        printf("\033[32;20H.");printf("\033[32;53H.");;fflush(stdout);sleep(4);
                        printf("\033[32;21H.");printf("\033[32;54H.");fflush(stdout);sleep(4);
                        printf("\033[32;22H.");printf("\033[32;55H.");fflush(stdout);sleep(4);


                        printf("\nAttendez encore un peu     |            Plat 2 pret");
                        printf("\033[33;24H.");fflush(stdout);sleep(4);
                        printf("\033[33;25H.");fflush(stdout);sleep(4);
                        printf("\033[33;26H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 pret!!!             |      Plat 2 pret depuis 1 min");

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n                __________\n                       ");
                         printf("             ****|   TOTAL  |****\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }

                else if(quan1!=0 && quan2==0 && quan3!=0)
                {
                    printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de salade et %d bols de \nfondant au chocolat.\n\n\n",quan1,quan2,quan3);
                         printf(" ___________________________________________________________\n");
                         printf("|        **** STATUS D'AVANCEMENT DES PLATS  ****           |\n");
                         printf("|___________________________________________________________|\n");

                         printf("Plat 1 en attente          |            Plat 3 en attente");
                         fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                        printf("\033[31;18H.");printf("\033[31;59H.");fflush(stdout);sleep(4);
                        printf("\033[31;19H.");printf("\033[31;60H.");fflush(stdout);sleep(4);
                        printf("\033[31;20H.");printf("\033[31;61H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 presque pret        |     Plat 3 pret(Ce dessert est rapide)");
                        printf("\033[32;20H.");fflush(stdout);sleep(4);
                        printf("\033[32;21H.");fflush(stdout);sleep(4);
                        printf("\033[32;22H.");fflush(stdout);sleep(4);

                        printf("\nAttendez encore un peu     |            Dessert deja pret!!!");
                        printf("\033[33;24H.");fflush(stdout);sleep(4);
                        printf("\033[33;25H.");fflush(stdout);sleep(4);
                        printf("\033[33;26H.");fflush(stdout);sleep(4);

                        printf("\nPlat 1 pret!!!             |      Plat 3 pret depuis 2 min au moins");

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\n                __________\n                       ");
                         printf("             ****|   TOTAL  |****\n");
                         printf("                  __________  ");
                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                }
    }


    else
    {
        printf("\nVous ne voulez rien commander. Fallait le dire plus haut quand on vous l'a demande.\nPas grave agreable journee a vous.");
    }



    printf("Voulez-vous repasser une commande? (Entrez 1 pour dire oui et 0 pour non) :"); scanf("%d",&choix);


    while(choix!=0)
    {
                printf("         \n***MENU***\n\n");
                printf("1- Salade Mediterraneenne- 6.50$ (Stock: 5)\n");
                printf("2- Poulet au Curry Doux- 12.9$ (Stock: 5)\n");
                printf("3- Fondant au chocolat- 5$ (Stock: 6)\n\n Regaler vous!!!\n\n");
                printf("Voulez-vous passer une commande? (Entrez 1 pour dire oui et 0 pour non) :"); scanf("%d",&choix);
                //on applique une taxe de 10%
                taxe=((6.5+12.9+5)*10)/100;

                if(choix==0)
                {
                    return 0;
                }


                printf("\nVoulez-vous le plat 1? :"); scanf("%d",&choix1);
                if(choix1==1)
                {
                    printf("Quantite(Nombre de plats) :");  scanf("%d",&quan1);
                    rst1=rst1-quan1;
                    while(quan1>5)
                    {
                        printf("Notre stock c'est 5 et vous demander une mauvaise quantite!!\nRetaper la quantite :");
                        scanf("%d",&quan1);
                    }
                }
                else
                {
                    printf("Il est pourtant bon mais ok.\n");
                }

                printf("\nVoulez-vous le plat 2? :"); scanf("%d",&choix2);
                if(choix2==1)
                {
                    printf("Quantite(Nombre de plats) :");  scanf("%d",&quan2);
                    rst2=rst2-quan2;
                    while(quan2>5)
                    {
                        printf("Notre stock c'est 5 et vous demander une mauvaise quantite!!\nRetaper la quantite :");
                        scanf("%d",&quan1);
                    }
                }
                else
                {
                    printf("Ne ratez pas ce delice mais ok c'est votre choix.\n");
                }

                printf("\nVoulez-vous le plat3? :");  scanf("%d",&choix3);

                if(choix3==1)
                {
                    rst3=rst3-quan3;
                    printf("Quantite(Nombre de plats) :");  scanf("%d",&quan3);
                    while(quan3>5)
                    {
                        printf("Notre stock c'est 5 et vous demander une mauvaise quantite!!\nRetaper la quantite :");
                        scanf("%d",&quan1);
                    }
                }
                else
                {
                    printf("Ok aucun dessert pour cette ravissante personne.\n");
                }


                //Preparation des commandes

                if(choix1==1 || choix2==1 || choix3==1)
                {
                            /*Meme en ayant decide de commander leur quantite peuvent etre des quantites nulles dont nos si
                            des choix dependront aussi des si des quantites*/

                            if(quan1!=0 && quan2!=0 && quan3!=0)
                            {
                                     printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d plats de salade, %d plats de poulets au curry et %d bols de \nfondant au chocolat.\n\n\n",quan1,quan2,quan3);
                                     printf(" _________________________________________________________________________________________________________\n");
                                     printf("|                                     **** STATUS D'AVANCEMENT DES PLATS  ****                            |\n");
                                     printf("|_________________________________________________________________________________________________________|\n");

                                     printf("Plat 1 en attente          |            Plat 2 en attente        |         Plat 3 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"



                                    printf("\033[31;18H.");printf("\033[31;59H.");printf("\033[31;95H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");printf("\033[31;60H.");printf("\033[31;96H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");printf("\033[31;61H.");printf("\033[31;97H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 presque pret        |     Plat 2 presque pret             |    Plat 3 pret(Ce dessert est rapide)");
                                    printf("\033[32;20H.");printf("\033[32;53H.");fflush(stdout);sleep(4);
                                    printf("\033[32;21H.");printf("\033[32;54H.");fflush(stdout);sleep(4);
                                    printf("\033[32;22H.");printf("\033[32;55H.");fflush(stdout);sleep(4);


                                    printf("\nAttendez encore un peu     |            Plat 2 pret              |     Dessert deja pret!!!");
                                    printf("\033[33;24H.");fflush(stdout);sleep(4);
                                    printf("\033[33;25H.");fflush(stdout);sleep(4);
                                    printf("\033[33;26H.");fflush(stdout);sleep(4);



                                    printf("\nPlat 1 pret!!!             |      Plat 2 pret depuis 1 min       |    Plat 3 pret depuis 2 min au moins");


                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n              __________\n                       ");
                                     printf("             ****|   TOTAL  |****\n");
                                     printf("                  __________  ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }

                            else if(quan1==0 && quan2==0 && quan3==0)
                            {
                                printf("\nVous n'avez en realite rien commande.\n, Pas grave, bonne suite a vous ,revenez quand vous voulez.");
                            }

                            else if(quan1==0 && quan2==0 && quan3!=0)
                            {
                                printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d bols de fondant au chocolat.\n\n\n",quan1,quan2,quan3);
                                     printf(" _________________________________________________________________________________________________________\n");
                                     printf("|                                     **** STATUS D'AVANCEMENT DES PLATS  ****                            |\n");
                                     printf("|_________________________________________________________________________________________________________|\n");

                                     printf("Plat 3 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"



                                    printf("\033[31;18H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 3 pret(Ce dessert est rapide)");

                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n              __________\n                       ");
                                     printf("             ****|   TOTAL  |****\n");
                                     printf("                  __________  ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }

                            else if(quan1==0 && quan2!=0 && quan3!=0)
                            {
                                printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d plats de poulets au curry et %d bols de \nfondant au chocolat.\n\n\n",quan1,quan2,quan3);
                                     printf(" _________________________________________________________________\n");
                                     printf("|         **** STATUS D'AVANCEMENT DES PLATS  ****                |\n");
                                     printf("|_________________________________________________________________|\n");

                                     printf("Plat 2 en attente        |         Plat 3 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"



                                    printf("\033[31;18H.");printf("\033[31;59H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");printf("\033[31;60H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");printf("\033[31;61H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 2 presque pret             |    Plat 3 pret(Ce dessert est rapide)");
                                    printf("\033[32;20H.");fflush(stdout);sleep(4);
                                    printf("\033[32;21H.");fflush(stdout);sleep(4);
                                    printf("\033[32;22H.");fflush(stdout);sleep(4);


                                    printf("\nPlat 2 pret              |     Dessert deja pret!!!");

                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n              __________\n                       ");
                                     printf("             ****|   TOTAL  |****\n");
                                     printf("                  __________  ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }

                            else if(quan1==0 && quan2!=0 && quan3==0)
                            {
                                     printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d plats de poulets au curry.\n\n\n",quan1,quan2,quan3);
                                     printf(" _____________________________________________________\n");
                                     printf("|  **** STATUS D'AVANCEMENT DES PLATS  ****           |\n");
                                     printf("|_____________________________________________________|\n");

                                     printf("Plat 2 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                                    printf("\033[31;18H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 2 presque pret");
                                    printf("\033[32;20H.");fflush(stdout);sleep(4);
                                    printf("\033[32;21H.");fflush(stdout);sleep(4);
                                    printf("\033[32;22H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 2 pret");

                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n              __________\n                       ");
                                     printf("             ****|   TOTAL  |****\n");
                                     printf("                  __________  ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }

                            else if(quan1!=0 && quan2==0 && quan3==0)
                            {
                                printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d plats de salade uniquement.\n\n\n",quan1,quan2,quan3);
                                     printf(" ______________________________________________________\n");
                                     printf("|     **** STATUS D'AVANCEMENT DES PLATS  ****         |\n");
                                     printf("|______________________________________________________|\n");

                                     printf("Plat 1 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                                    printf("\033[31;18H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 presque pret");
                                    printf("\033[32;20H.");fflush(stdout);sleep(4);
                                    printf("\033[32;21H.");fflush(stdout);sleep(4);
                                    printf("\033[32;22H.");fflush(stdout);sleep(4);


                                    printf("\nAttendez encore un peu");
                                    printf("\033[33;24H.");fflush(stdout);sleep(4);
                                    printf("\033[33;25H.");fflush(stdout);sleep(4);
                                    printf("\033[33;26H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 pret!!!");

                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n              __________\n                       ");
                                     printf("             ****|   TOTAL  |****\n");
                                     printf("                  __________  ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }

                            else if(quan1!=0 && quan2!=0 && quan3==0)
                            {
                                printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d plats de salade et %d plats de poulets au curry.\n\n\n",quan1,quan2,quan3);
                                     printf(" _______________________________________________________________\n");
                                     printf("|        **** STATUS D'AVANCEMENT DES PLATS  ****               |\n");
                                     printf("|_______________________________________________________________|\n");

                                     printf("Plat 1 en attente          |            Plat 2 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                                    printf("\033[31;18H.");printf("\033[31;59H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");printf("\033[31;60H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");printf("\033[31;61H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 presque pret        |     Plat 2 presque pret");
                                    printf("\033[32;20H.");printf("\033[32;53H.");;fflush(stdout);sleep(4);
                                    printf("\033[32;21H.");printf("\033[32;54H.");fflush(stdout);sleep(4);
                                    printf("\033[32;22H.");printf("\033[32;55H.");fflush(stdout);sleep(4);


                                    printf("\nAttendez encore un peu     |            Plat 2 pret");
                                    printf("\033[33;24H.");fflush(stdout);sleep(4);
                                    printf("\033[33;25H.");fflush(stdout);sleep(4);
                                    printf("\033[33;26H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 pret!!!             |      Plat 2 pret depuis 1 min");

                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n              __________\n                       ");
                                     printf("             ****|   TOTAL  |****\n");
                                     printf("                  __________  ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }

                            else if(quan1!=0 && quan2==0 && quan3!=0)
                            {
                                printf("\n***Recapitulatif de votre commande***\n\n");
                                     printf("Vous avez commande %d plats de salade et %d bols de \nfondant au chocolat.\n\n\n",quan1,quan2,quan3);
                                     printf(" ___________________________________________________________\n");
                                     printf("|        **** STATUS D'AVANCEMENT DES PLATS  ****           |\n");
                                     printf("|___________________________________________________________|\n");

                                     printf("Plat 1 en attente          |            Plat 3 en attente");
                                     fflush(stdout);// Pour forcer l'affichage immédiat de "plat 1 en attente"

                                    printf("\033[31;18H.");printf("\033[31;59H.");fflush(stdout);sleep(4);
                                    printf("\033[31;19H.");printf("\033[31;60H.");fflush(stdout);sleep(4);
                                    printf("\033[31;20H.");printf("\033[31;61H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 presque pret        |     Plat 3 pret(Ce dessert est rapide)");
                                    printf("\033[32;20H.");fflush(stdout);sleep(4);
                                    printf("\033[32;21H.");fflush(stdout);sleep(4);
                                    printf("\033[32;22H.");fflush(stdout);sleep(4);

                                    printf("\nAttendez encore un peu     |            Dessert deja pret!!!");
                                    printf("\033[33;24H.");fflush(stdout);sleep(4);
                                    printf("\033[33;25H.");fflush(stdout);sleep(4);
                                    printf("\033[33;26H.");fflush(stdout);sleep(4);

                                    printf("\nPlat 1 pret!!!             |      Plat 3 pret depuis 2 min au moins");

                                     somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                                     printf("\n\n");
                                     printf("            _________\n ");
                                     printf("           |   TOTAL |\n");
                                     printf("            _________ ");
                                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);

                            }
                }


                else
                {
                    printf("\nVous ne voulez rien commander. Fallait le dire plus haut quand on vous l'a demande.\nPas grave agreable journee a vous.");
                }


                printf("Voulez-vous repasser une commande? (Entrez 1 pour dire oui et 0 pour non) :"); scanf("%d",&choix);

    }





    return 0;
}
