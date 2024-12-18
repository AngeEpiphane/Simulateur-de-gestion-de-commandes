#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>


int main()
{
    int  choix,choix1,choix2,choix3,quan1,quan2,quan3,i,tour;
    int rst1=5, rst2=5, rst3=6;
    float taxe,somme,total;


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


    printf("Voulez-vous le plat 1? :"); scanf("%d",&choix1);
    if(choix1==1)
    {
        rst1=rst1-quan1;
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan1);
    }
    else
    {
        printf("Il est pourtant bon mais ok.\n");
    }

    printf("\nVoulez-vous le plat 2? :"); scanf("%d",&choix2);
    if(choix2==1)
    {
        rst2=rst2-quan2;
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan2);
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
    }
    else
    {
        printf("Ok aucun dessert pour cette ravissante personne.\n");
    }


    //Preparation des commandes

    if(choix1==1 && choix2==1 && choix3==1)
    {
                if(quan1!=0 || quan2!=0 || quan3!=0)
                {
                         printf("\n***Recapitulatif de votre commande***\n\n");
                         printf("Vous avez commande %d plats de salade, %d plats de poulets au curry et %d bols de \nfondant au chocolat.\n",quan1,quan2,quan3);

                         printf("Plat 1 en attente1");

                         tour=0;

                         while(tour<3)
                         {
                            for(i=1;i<=3;i++)
                            {
                                printf(".");
                                sleep(4);
                            }
                            tour++;
                            if(tour==1)
                            {
                                printf("\nPlat 1 presque pret");
                            }
                            else if(tour==2)
                            {
                                printf("\nAttendez encore un peu");
                            }
                            else if(tour==3)
                            {
                                printf("\nPlat 1 pret!!!");
                            }

                         }

                         somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                         printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);
        
                }
                else if(quan1==0 && quan2==0 && quan3==0)
                {
                    printf("\nVous n'avez en realite rien commande. Pas grave, bonne suite a vous.");
                }
    }
    
    
    else if(choix1==0 && choix2==0 && choix3==0)
    {
        printf("\nVous ne voulez rien commander. Fallait le dire plus haut quand on vous l'a demande.\nPas grave agreable journee a vous.");
    }
    
    
    else if(choix==1 && choix2==1 && choix3==0)
    {
    
                if(quan1!=0 || quan2!=0 || quan3!=0)
                {
                    printf("\n***Recapitulatif de votre commande***\n\n");
                    printf("Vous avez commande %d plats de salade, %d plats de poulets au curry et %d bols de \nfondant au chocolat.\n",quan1,quan2,quan3);

                    printf("Plat 1 en attente1");  printf("Plat")

                    tour=0;

                     while(tour<3)
                     {
                        for(i=1;i<=3;i++)
                        {
                            printf(".");
                            sleep(4);
                        }
                        tour++;
                        if(tour==1)
                        {
                            printf("\nPlat 1 presque pret");
                        }
                        else if(tour==2)
                        {
                            printf("\nAttendez encore un peu");
                        }
                        else if(tour==3)
                        {
                            printf("\nPlat 1 pret!!!");
                        }

                     }

                    somme=(6.5*quan1+12.9*quan2+5*quan3); total=somme+taxe;

                     printf("\n\nVotre commande fait un total de %.2f$ . Merci pour tout.\n\n",total);
                    
                    
                }
                else if(quan1==0 && quan2==0 && quan3==0)
                {
                    printf("\nVous n'avez en realite rien commande. Pas grave, bonne suite a vous.");
                }
        
    }
    else if(choix1==1 && choix2==0 && choix3==1)
    
    
    

    return 0;
}
