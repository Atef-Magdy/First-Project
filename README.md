# First-Project
subtracting squares game

import pygame ,sys
from pygame.locals import *
pygame.init()
import time
import random
#______________________________________________
screen=pygame.display.set_mode((800,600),0,32)
pygame.display.set_caption("Subtracting Squares")
#
r=random.randrange(21,100)
constant=str(r)
value=str(r)
#Colors
white=(255,255,255)
black=(0,0,0)
blue=(0,0,200)
light_blue=(0,0,255)
green=(0,160,0)
light_green=(0,255,0)
#Fonts
font=pygame.font.Font(None,40)
font1=pygame.font.Font(None,60)
font2=pygame.font.Font('C:/Windows/Fonts/LCALLIG.TTF',90)
font3=pygame.font.Font('C:/Windows/Fonts/LCALLIG.TTF',50)
font4=pygame.font.Font(None,30)
font5=pygame.font.Font(None,25)
#Messages
coins=font.render("coins $: ",True,black)
coins_masg=font.render("the value of coins will be in random",True,black)
remaining=font.render("Remaining :",True,black)
player1=font1.render("Player_1",True,black,green)
player1_light=font1.render("Player_1",True,black,light_green)
player2=font1.render("Player_2",True,black,green)
player2_light=font1.render("Player_2",True,black,light_green)
masg1=font1.render("player_1 wins",True,black)
masg2=font1.render("player_2 wins",True,black)
welcome=font2.render("Welcome",True,light_green)
welcome2=font3.render("To Subtracting Squares game",True,light_green)
condition=font.render("Press p to play or q to quit",True,black)
my_name=font4.render("written by Atef el Programmer el gamed gdn ^-^",True,black)
project=font5.render("First project in programming_1" ,True,black)
project2=font5.render("Supervised by Dr.Al-Ramly ",True,black)
#
x1=font.render("1",True,black)
x2=font.render("4",True,black)
x3=font.render("9",True,black)
x4=font.render("16",True,black)
x5=font.render("25",True,black)
x6=font.render("36",True,black)
x7=font.render("49",True,black)
x8=font.render("64",True,black)
#
value=font.render(value,True,black)
constant=font.render(constant,True,black)
click=pygame.mouse.get_pressed()
i=0
#Introduction
while True:
        choice=False
        for event in pygame.event.get():
                if event.type==QUIT:
                        pygame.quit()
                        sys.exit()
                if event.type==KEYDOWN:
                        if event.key==K_p:
                                choice=True
                        elif event.key==K_q:
                                pygame.quit()
                                sys.exit()
        if choice==True:
                break
        screen.fill(white)
        
        screen.blit(welcome,(175,70))
        screen.blit(welcome2,(10,200))
        screen.blit(condition,(215,350))
        pygame.draw.line(screen,black,(0,560),(800,560),3)
        pygame.draw.line(screen,black,(500,560),(500,600),3)
        screen.blit(my_name,(10,570))
        screen.blit(project,(525,562))
        screen.blit(project2,(540,582))
        pygame.display.update()
#Game_Loop         
player_1=True
player_2=False
while True:
        screen.fill(white)
        for event in pygame.event.get():
            if event.type==QUIT:
                pygame.quit()
                sys.exit()
            
            if event.type == MOUSEBUTTONDOWN:
                x,y = event.pos
                if 190<x<280 and 90<y<140:
                    if r>=1:
                        r-=1
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 285<x<375 and 90<y<140:
                    if r>=4:
                        r-=4
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 380<x<470 and 90<y<140:
                    if r>=9:
                        r-=9
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 475<x<565 and 90<y<140:
                    if r>=16:
                        r-=16
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 190<x<280 and 150<y<200:
                    if r>=25:
                        r-=25
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 285<x<375 and 150<y<200:
                    if r>=36:
                        r-=36
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 380<x<470 and 150<y<200:
                    if r>=49:
                        r-=49
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                elif 475<x<565 and 150<y<200:
                    if r>=64:
                        r-=64
                        value=str(r)
                        value=font.render(value,True,black)
                        i+=1
                if i%2==0:
                        player_1=True
                        player_2=False
                else:
                        player_1=False
                        player_2=True
                pygame.display.update()
        #_____________________________________________________________
        pos=pygame.mouse.get_pos()
        if 190<pos[0]<190+90 and 90<pos[1]<90+50:
            pygame.draw.rect(screen,light_green,Rect((190,90),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((190,90),(90,50)))
        if 285<pos[0]<285+90 and 90<pos[1]<90+50:
            pygame.draw.rect(screen,light_green,Rect((285,90),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((285,90),(90,50)))
        if 380<pos[0]<380+90 and 90<pos[1]<90+50:
            pygame.draw.rect(screen,light_green,Rect((380,90),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((380,90),(90,50)))
        if 475<pos[0]<475+90 and 90<pos[1]<90+50:
            pygame.draw.rect(screen,light_green,Rect((475,90),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((475,90),(90,50)))
        if 190<pos[0]<190+90 and 150<pos[1]<150+50:
            pygame.draw.rect(screen,light_green,Rect((190,150),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((190,150),(90,50)))
        if 285<pos[0]<285+90 and 150<pos[1]<150+50:
            pygame.draw.rect(screen,light_green,Rect((285,150),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((285,150),(90,50)))
        if 380<pos[0]<380+90 and 150<pos[1]<150+50:
            pygame.draw.rect(screen,light_green,Rect((380,150),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((380,150),(90,50)))
        if 475<pos[0]<475+90 and 150<pos[1]<150+50:
            pygame.draw.rect(screen,light_green,Rect((475,150),(90,50)))
        else:
            pygame.draw.rect(screen,blue,Rect((475,150),(90,50)))
       #______________________________________________________________
        if player_1==True:
                screen.blit(player1_light,(290,340))
                screen.blit(player2,(290,400))
        if player_2==True:
                screen.blit(player1,(290,340))
                screen.blit(player2_light,(290,400))
        #
        screen.blit(x1,(225,105))
        screen.blit(x2,(320,105))
        screen.blit(x3,(415,105))
        screen.blit(x4,(505,105))
        screen.blit(x5,(220,165))
        screen.blit(x6,(315,165))
        screen.blit(x7,(410,165))
        screen.blit(x8,(505,165))
        #
        screen.blit(coins_masg,(150,5))
        screen.blit(coins,(310,50))
        screen.blit(constant,(420,50))
        screen.blit(value,(445,255))
        screen.blit(remaining,(275,255))
        #
        if r==0:
           if i%2==0:
               screen.fill(white)
               screen.blit(masg2,(250,250))
           else:
               screen.fill(white)
               screen.blit(masg1,(250,250))
        pygame.display.update()
        


    
