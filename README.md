#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <conio.h>
int hp, sp;
int mHP=100;
void characterDesign(int avatar){
if (avatar == 1){
    hp = 500;
    sp = 100;
    }else if (avatar == 2){
    hp = 100;
    sp = 500;
    }else{
    hp = 250;
    sp = 250;
    }
}
    void attack(){
    int dmg;
    dmg = rand()%50;
    mHP = mHP- dmg;
    printf("\n Damage Dealt : %d", dmg);
    if(mHP < 0)
        mHP = 0;
    printf("\nMonster HP Remains: %d", mHP);
    printf("\nYour Remain HP: %d", hp);
    printf("\nYour Remain SP: %d", sp);
    }
    void mAttack(){
    int dmg = rand()%100;
    hp = hp - dmg;
    printf("\n\n Enemy turn");
    printf("\nYour Received %d Damage", dmg);
    printf("\n Your Remain Hp : %d", hp);
    }

int main()
{
    srand ((unsigned)time (NULL));
    int avatar, atk, dmg;
    printf("\t\t\t********** GAME START **********");
    printf("\n\n In This game you have to invited by God. because in another world Demand Lord are arrived and his army are attacking normal people. \nDemand Lord captured half of world though there brutel. \nGod reincarnate you in another world for defeat . ");
    printf("\nChoose your Avatar.");
    while(1){
        printf("\n 1.Worrier\n 2.Wizard \n 3.Gunner \n\nYour own Option\n");
        scanf("%d", &avatar);

    if (avatar == 1 || avatar == 2 || avatar == 3){
        characterDesign (avatar);
        printf("\nYour HP: %d", hp);
        printf("\nYour HP: %d", sp);
        printf("\n\t\t GAME START\n\n");
        printf("\n A MONSTER APPEARED");
        while(1){
            printf("\n\n 1.Attack(10 HP) \n 2.Normal Magic(10 SP) \n 3. Spells(unknown)");
            scanf("%d", & atk);
            switch(atk){
            case 1:
                hp = hp - 10;
                system ("cls");
                attack();
                mAttack();
                break;
            case 2:
                sp = sp - 10;
                system ("cls");
                attack();
                mAttack();
                break;
            case 3:
                sp = sp -(10+(rand()%80));
                dmg = 50 + rand ()% 101;
                mHP = mHP - dmg;
                system ("cls");
                printf("\n Damage Dealt : %d", dmg);
                if(mHP<0)
                    mHP = 0;
                printf("\nMonster HP remains: %d", mHP);
                printf("\nYour Remains HP: %d", mHP);
                printf("\nYour Remains SP: %d", mHP);
                mAttack();

                default:
                printf("\n Choose Correct Option:");
            }
            if (mHP <= 0 || hp <= 0)
                break;
        }
        if (hp <= 0)
        {
            printf("\n GAME OVER");
        }
        else if (mHP <= 0){
            printf("\n CONGRUTULATION YOU WON!! ");
        }
        break;

    }else {
    printf("\n Choose Correct Option");
    }
    }
        return 0;
}
