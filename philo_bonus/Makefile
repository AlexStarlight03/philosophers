# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: adube <adube@student.42.fr>                +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/10/27 15:26:59 by adube             #+#    #+#              #
#    Updated: 2023/10/27 15:28:29 by adube            ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

# *********************************** RULES ********************************** #
NAME := philo_bonus

HEADER	:= -I ./include_bonus

SRC_DIR := ./src_bonus

OBJ_DIR := ./obj

SRC_MAIN =	$(SRC_DIR)/main_bonus.c \
				$(SRC_DIR)/actions_bonus.c \
				$(SRC_DIR)/utils_bonus.c 

OBJ_MAIN := $(patsubst $(SRC_DIR)/%.c, $(OBJ_DIR)/%.o, $(SRC_MAIN))

CC := gcc
CFLAGS := -Wextra -Wall -Werror -g
RM := rm -rf

# *********************************** RULES ********************************** #

all: $(NAME)
	@echo "-- Philo Bonus created --"

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	@$(CC) $(CFLAGS) -o $@ -c $< $(HEADER)

$(NAME): $(OBJ_DIR) $(OBJ_MAIN)
	@$(CC) $(OBJ_MAIN) $(HEADER) -o $(NAME)

$(OBJ_DIR):
	@mkdir $@

clean:
	@$(RM) $(OBJ_DIR)
	@echo "-- Clean done --"

fclean: clean
	@$(RM) $(NAME)
	@echo "-- Fclean done --"

re: fclean all

# Run norminette
norm :
	@echo "\n$W>>>>>>>>> $YNORMINETTE $W<<<<<<<<<<<$Z\n"
	@norminette $(SRC_MAIN) $(HEADER)
	@echo "\n$W>>>>>>>>> $YNORMINETTE DONE $W<<<<<<"


.PHONY: all, clean, fclean, re, bonus