# RPG
This is our robot to get the pom poms
#include <kipr/wombat.h>
//motor right zero, motor left 2
int main()
{
    wait_for_light(0);

    int left = 1300;
    int straight = 1000;
    int right = 1300;
    while (analog(1) < 1600)
    {
        mav(0,1500);
        mav(2,1500);
        msleep(100);
    }
    ao();
    mav(0,-1500);
    mav(2,1500);
    msleep(800);
    cmpc(0);
    while(gmpc(0)< 17000)
    {
        if (analog(1)<1600)
        {
            mav(0,1500);
            mav(2, straight);
        }
        else
        {
            mav(0,straight);
            mav(2,1300);
        }
    }
    mav(0,-1500);
    mav(2,-1500);
    msleep(500);
    mav(0,750);
    mav(2,750);
    msleep(1000);
    mav(0,1500);
    mav(2,1500);
    msleep(700);
    mav(0,-1500);
    mav(2,-1500);
    msleep(1000);
    mav(0,1500);
    mav(2,1500);
    msleep(2000);
    ao;

    return 0;
}
