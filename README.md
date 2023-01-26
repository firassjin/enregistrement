# enregistrement
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
                                     // creation d'un nouveau type de donnee
    typedef struct date
    {
        int d,m,y;
    } date ;

    typedef struct livre
    {
        int isbn ;
        char nom[20];
        char prenom[20];
        char titre[50];
        date dat ;
        char mde[50];

    } livre ;
int main()
{
                                                      // declaration des variables
int i,n,supp,l,j,k,choix,modif,cher;
livre liv[1000];


 do
    {
         printf("     Choisir une operation \n \n");
         printf("0: Remplir les informations d'un livre \n \n");
         printf("1: Ajouter les informations d'un livre \n \n");
         printf("2: Modifier les informations d'un livre \n \n");
         printf("3: Supprimer les informations d'un livre \n \n");
         printf("4: Afficher les informations d'un livre \n \n");
         printf("5: chercher un livre on intoduisant sant isbn \n \n");
         printf("6: Quitter le programme \n \n");
         scanf("%d",&choix);
        // system("cls")

    switch(choix)
   {
       case 0:
              // la saisie des  informations des livres

     printf("donner le nombre de liver à saisir\n");
     scanf("%d",&n);
     for(i=0;i<n;i++)
{
    printf("donner le isbn %d \n",i+1);
    scanf("%d",&liv[i].isbn);
    printf("donner le nom de l'auteur %d \n",i+1);
    scanf("%s",liv[i].nom);
    printf("donner le prenom de l'auteur%d \n",i+1);
    scanf("%s",liv[i].prenom);
    printf("donner le titre du livre %d \n",i+1);
    scanf("%s",liv[i].titre);
    printf("donner la date jj mm aaaa de publication %d \n",i+1);
    scanf("%d %d %d",&liv[i].dat.d,&liv[i].dat.m,&liv[i].dat.y);
    printf("donner  la maison d'edition %d \n",i+1);
    scanf("%s",liv[i].mde);

}
break;

          case 1:
                  // l'ajout des  informations des livr

    printf("donner le isbn à ajouter %d \n",n);
    scanf("%d",&liv[n].isbn);
    printf("donner le nom de l'auteur %d \n",n);
    scanf("%s",liv[n].nom);
    printf("donner le prenom de l'auteur%d \n",n);
   scanf("%s",liv[n].prenom);
    printf("donner le titre du livre %d \n",n);
    scanf("%s",liv[n].titre);
    printf("donner la date jj mm aaaa de publication %d \n",n);
    scanf("%d %d %d",&liv[n].dat.d,&liv[n].dat.m,&liv[n].dat.y);
    printf("donner  la maison d'edition %d \n",n);
    scanf("%s",liv[n].mde);
 n++;

break;
        case 2:
                // modifocation d'un element

                k=0;
    printf("donnee le isbn du livre à modifier ");
    scanf("%d",&modif);

    for(i=0;i<n;i++)
    {
        l=liv[i].isbn;

        if (modif==l)
        {
    printf("donner le nouveau isbn  %d \n",i+1);
    scanf("%d",&liv[i].isbn);
    printf("donner le nouveau nom de l'auteur %d \n",i+1);
    scanf("%s",liv[i].nom);
    printf("donner le nouveau prenom de l'auteur%d \n",i+1);
   scanf("%s",liv[i].prenom);
    printf("donner le nouveau titre du livre %d \n",i+1);
    scanf("%s",liv[i].titre);
     printf("donner la  nouvalle date jj mm aaaa de publication %d \n",i+1);
    scanf("%d %d %d",&liv[i].dat.d,&liv[i].dat.m,&liv[i].dat.y);
    printf("donner  la nouvelle maison d'edition %d \n",i+1);
    scanf("%s",liv[i].mde);
          k=1;
          break;
            }
        }
  if(k!=1)
    {
        printf("le isbn %d n existe pas",modif);
  }

break;

        case 3:
                // suppretion un element

                k=0;
    printf("donnee la isbn du livre à supprimer ");
    scanf("%d",&supp);

    for(i=0;i<n;i++)
    {
        l=liv[i].isbn;

        if (supp==l)
        {


             for(j=i;j<n;j++)
            {
                liv[j]=liv[j+1];

            }
          k=1;
          break;
        }
    }
  if(k==1)
    {
        n--;
  }
  else

    {
        printf("le isbn %d n existe pas",supp);
    }
break;

            case 4:
                    // affichage de toutes les donner
    for(i=0;i<n;i++)
{
    printf("livre n°= %d \n",i+1);

    printf("isbn :%d\n",liv[i].isbn);

    printf("nom de l'auteur :%s \n",liv[i].nom);

    printf("le prenom de l'auteur :%s \n",liv[i].prenom);

    printf("le titre du livre :%s \n",liv[i].titre);

    printf("la date de publication : %d/%d/%d \n",liv[i].dat.d,liv[i].dat.m,liv[i].dat.y);

    printf("la maison d'edition :%s\n",liv[i].mde);

}
break;

 case 5:
                // rechercher un element

                 k=0;
    printf("donnee le isbn du livre à rchercher ");
    scanf("%d",&cher);

    for(i=0;i<n;i++)
    {
        l=liv[i].isbn;

        if (cher==l)
        {
    printf("livre n°= %d \n",i+1);

    printf("isbn :%d\n",liv[i].isbn);

    printf("nom de l'auteur :%s \n",liv[i].nom);

    printf("le prenom de l'auteur :%s \n",liv[i].prenom);

    printf("le titre du livre :%s \n",liv[i].titre);

    printf("la date de publication : %d/%d/%d \n",liv[i].dat.d,liv[i].dat.m,liv[i].dat.y);

    printf("la maison d'edition :%s\n",liv[i].mde);
          k=1;
          break;
            }
        }
  if(k!=1)
    {
        printf("le isbn %d n existe pas",cher);
  }

break;


         case 6:
             //quitter ke programme
    printf("fin du programme");
    break;

}

}
    while(choix!=6);

    return 0;
}
