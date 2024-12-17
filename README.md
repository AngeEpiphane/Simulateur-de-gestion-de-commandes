#include <stdio.h>
#include <stdlib.h>

int main()
{
    int choix,quan1,quan2,quan3;
    int rst1=5, rst2=5, rst3=6;
    
    printf("     Bienvenue a Angi's Meal!!!\n\n");
    printf("           ***MENU***\n\n");
    printf("1- Salade Mediterraneenne- 6.50$ (Stock: 5)\n");
    printf("2- Poulet au Curry Doux- 12.9$ (Stock: 5)\n");
    printf("3- Fondant au chocolat- 5$ (Stock: 6)\n\n Regaler vous!!!\n\n");
    printf("Voulez-vous passer une commande? (Entrez 1 pour dire oui et 0 pour non :"); scanf("%d",&choix);
    if(choix==0)
    {
        return 0;
    }
    
    
    printf("Voulez-vous le plat 1? :"); scanf("%d",&choix);
    if(choix==1)
    {
        rst1=rst1-quan1;
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan1);
    }
    else
    {
        printf("Il est pourtant bon mais ok.\n\n");
    }
    
    printf("\nVoulez-vous le plat 2? :"); scanf("%d",&choix);
    if(choix==1)
    {
        rst2=rst2-quan2;
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan1);
    }
    else
    {
        printf("Ne ratez pas ce delice mais ok c'est votre choix.\n\n");
    }

    printf("\nVoulez-vous le plat3? :");  scanf("%d",&choix);
    
    if(choix==1)
    {
        rst3=rst3-quan3;
        printf("Quantite(Nombre de plats) :");  scanf("%d",&quan1);
    }
    else
    {
        printf("Ok aucun dessert pour cette ravissante personne.\n\n");
    }
    
    return 0;
}
