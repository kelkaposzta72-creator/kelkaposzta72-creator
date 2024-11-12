- 👋 Himport pygame
import time
import random

# Színek
WHITE = (255, 255, 255)
YELLOW = (255, 255, 102)
BLACK = (, , )
RED = (213, 50, 80)
GREEN = (, 255, )
BLUE = (50, 153, 213)

# Beállítások
WIDTH = 600
HEIGHT = 400
SNAKE_BLOCK = 10
SNAKE_SPEED = 15

# Inicializálás
pygame.init()

# Képernyő beállítása
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption('Kígyós Játék')

# Kígyó
clock = pygame.time.Clock()

def draw_snake(snake_block, snake_list):
    for x in snake_list:
        pygame.draw.rect(screen, random.choice([GREEN, BLUE, YELLOW, RED]), [x[], x[1], snake_block, snake_block])

def message(msg, color):
    font_style = pygame.font.SysFont("bahnschrift", 25)
    mesg = font_style.render(msg, True, color)
    screen.blit(mesg, [WIDTH / 6, HEIGHT / 3])

def game_loop():
    game_over = False
    game_close = False

    x1 = WIDTH / 2
    y1 = HEIGHT / 2

    x1_change = 
    y1_change = 

    snake_list = []
    snake_length = 1

    foodx = round(random.randrange(, WIDTH - SNAKE_BLOCK) / 10.) * 10.
    foody = round(random.randrange(, HEIGHT - SNAKE_BLOCK) / 10.) * 10.

    while not game_over:

        while game_close == True:
            screen.fill(BLACK)
            message("Véged van! Nyomj Q-t a kilépéshez vagy C-t az újrakezdéshez", RED)
            pygame.display.update()

            for event in pygame.event.get():
                if event.type == pygame.KEYDOWN:
                    if event.key == pygame.K_q:
                        game_over = True
                        game_close = False
                    if event.key == pygame.K_c:
                        game_loop()

        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                game_over = True
            if event.type == pygame.KEYDOWN:
                if event.key == pygame.K_LEFT:
                    x1_change = -SNAKE_BLOCK
                    y1_change = 
                elif event.key == pygame.K_RIGHT:
                    x1_change = SNAKE_BLOCK
                    y1_change = 
                elif event.key == pygame.K_UP:
                    y1_change = -SNAKE_BLOCK
                    x1_change = 
                elif event.key == pygame.K_DOWN:
                    y1_change = SNAKE_BLOCK
                    x1_change = 

        if x1 >= WIDTH or x1 <  or y1 >= HEIGHT or y1 < :
            game_close = True

        x1 += x1_change
        y1 += y1_change
        screen.fill(BLUE)
        pygame.draw.rect(screen, GREEN, [foodx, foody, SNAKE_BLOCK, SNAKE_BLOCK])
        snake_head = []
        snake_head.append(x1)
        snake_head.append(y1)
        snake_list.append(snake_head)
        if len(snake_list) > snake_length:
            del snake_list[]

        for x in snake_list[:-1]:
            if x == snake_head:
                game_close = True

        draw_snake(SNAKE_BLOCK, snake_list)

        pygame.display.update()

        if x1 == foodx and y1 == foody:
            foodx = round(random.randrange(, WIDTH - SNAKE_BLOCK) / 10.) * 10.
            foody = round(random.randrange(, HEIGHT - SNAKE_BLOCK) / 10.) * 10.
            snake_length += 1

        clock.tick(SNAKE_SPEED)

    pygame.quit()
    quit()

if __name__ == "__main__":
    game_loop()
    i, I’m @kelkaposzta72-creator
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
kelkaposzta72-creator/kelkaposzta72-creator is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
