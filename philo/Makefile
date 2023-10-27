# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: adube <adube@student.42.fr>                +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/09/21 09:33:12 by adube             #+#    #+#              #
#    Updated: 2023/10/27 15:20:22 by adube            ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

# *********************************** RULES ********************************** #
NAME := philo

HEADERS	:= -I ./include

SRC_DIR := ./src

OBJ_DIR := ./obj

SRC_MAIN =	$(SRC_DIR)/main.c \
				$(SRC_DIR)/actions.c \
				$(SRC_DIR)/utils.c 

OBJ_MAIN := $(patsubst $(SRC_DIR)/%.c, $(OBJ_DIR)/%.o, $(SRC_MAIN))

CC := gcc
CFLAGS := -Wextra -Wall -Werror -g
RM := rm -rf

# *********************************** RULES ********************************** #

all: $(NAME)
	@echo "-- Philo created --"

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	@$(CC) $(CFLAGS) -o $@ -c $< $(HEADERS)

$(NAME): $(OBJ_DIR) $(OBJ_MAIN)
	@$(CC) $(OBJ_MAIN) $(HEADERS) -o $(NAME)

$(OBJ_DIR):
	@mkdir $@

clean:
	@$(RM) $(OBJ_DIR)

fclean: clean
	@$(RM) $(NAME)

re: fclean all

# Run norminette
norm :
	@echo "\n$W>>>>>>>>> $YNORMINETTE $W<<<<<<<<<<<$Z\n"
	@norminette $(SRC_MAIN) $(HEADER)
	@echo "\n$W>>>>>>>>> $YNORMINETTE DONE $W<<<<<<"


.PHONY: all, clean, fclean, re, bonus