# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: hmunoz-g <hmunoz-g@student.42barcelon      +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2024/10/16 16:17:09 by hmunoz-g          #+#    #+#              #
#    Updated: 2024/10/16 18:08:38 by hmunoz-g         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = libftprintf.a
CC = cc
FLAGS = -Werror -Wall -Wextra -g
LIBFTDIR = libft/
OBJ_DIR = obj/
SRCS_DIR = srcs/
BONUS_DIR = srcs/bonus/
RM = rm -f

# Colors
DEF_COLOR = \033[0;39m
GRAY = \033[0;90m
RED = \033[0;91m
GREEN = \033[0;92m
YELLOW = \033[0;93m
BLUE = \033[0;94m
MAGENTA = \033[0;95m
CYAN = \033[0;96m
WHITE = \033[0;97m
# End of colors

SRCS =	srcs/ft_printf.c \
	srcs/ft_starter.c \
	srcs/managers/ft_com_managers.c \
	srcs/managers/ft_itoa_printf.c \
	srcs/managers/ft_itoa_printf_u.c \
	srcs/managers/ft_itoa_printf_x.c \
	srcs/managers/ft_putstr_fd_print.c \
	srcs/managers/ft_putchar_fd_print.c \
	srcs/managers/ft_putnbase_fd.c \
	srcs/parser/ft_condition_checker.c \
	srcs/parser/ft_flag_checker.c \
	srcs/parser/ft_parser.c \
	srcs/printers/ft_printf_c.c \
	srcs/printers/ft_printf_di.c \
	srcs/printers/ft_printf_p.c \
	srcs/printers/ft_printf_s.c \
	srcs/printers/ft_printf_u.c \
	srcs/printers/ft_printf_x.c

BONUS_SRCS = srcs/ft_printf.c \
	srcs/ft_starter.c \
	srcs/managers/ft_com_managers.c \
	srcs/managers/ft_itoa_printf.c \
	srcs/managers/ft_itoa_printf_u.c \
	srcs/managers/ft_itoa_printf_x.c \
	srcs/managers/ft_putstr_fd_print.c \
	srcs/managers/ft_putchar_fd_print.c \
	srcs/managers/ft_putnbase_fd.c \
	srcs/parser/ft_condition_checker.c \
	srcs/parser/ft_flag_checker.c \
	srcs/parser/ft_parser.c \
	srcs/bonus/ft_printf_c_bonus.c \
	srcs/bonus/ft_printf_di_bonus.c \
	srcs/bonus/ft_printf_di_functions_bonus.c \
	srcs/bonus/ft_printf_p_bonus.c \
	srcs/bonus/ft_printf_p_functions_bonus.c \
	srcs/bonus/ft_printf_s_bonus.c \
	srcs/bonus/ft_printf_s_functions_bonus.c \
	srcs/bonus/ft_printf_u_bonus.c \
	srcs/bonus/ft_printf_u_functions_bonus.c \
	srcs/bonus/ft_printf_x_bonus.c \
	srcs/bonus/ft_printf_x_functions_bonus.c

OBJS  = ${SRCS:.c=.o}
BONUS_OBJS = ${BONUS_SRCS:.c=.o}

LIBFT_OBJS = $(addprefix $(LIBFTDIR), \
	ft_itoa.o \
	ft_strchr.o \
	ft_strdup.o \
	ft_strjoin.o \
	ft_strmapi.o \
	ft_strnstr.o \
	ft_strchr.o \
	ft_strrchr.o \
	ft_substr.o \
	ft_split.o \
	ft_atoi.o \
	ft_isalnum.o \
	ft_isalpha.o \
	ft_isascii.o \
	ft_isdigit.o \
	ft_isprint.o \
	ft_isspace.o \
	ft_isvalidsign.o \
	ft_memcmp.o \
	ft_tolower.o \
	ft_toupper.o \
	ft_strncmp.o \
	ft_strlcat.o \
	ft_strlcpy.o \
	ft_strlen.o \
	ft_bzero.o \
	ft_calloc.o \
	ft_memchr.o \
	ft_memcpy.o \
	ft_memmove.o \
	ft_memset.o \
	ft_putchar_fd.o \
	ft_putendl_fd.o \
	ft_putnbr_fd.o \
	ft_putstr_fd.o \
	ft_striteri.o \
	ft_strtrim.o \
	ft_free.o \
	get_next_line.o)

INCLUDE = -L ./libft -lft

%.o: %.c Makefile includes/ft_printf.h libft/libft.h
	${CC} -I. -c $< -o ${<:.c=.o}
	@echo "${YELLOW}Compiling: $< ${DEF_COLOR}"

all: ${NAME}

${NAME}: ${OBJS} ${LIBFT_OBJS}
	@echo "${CYAN} Building ${NAME}! ${DEF_COLOR}"
	make -C ${LIBFTDIR}  # Ensure libft is built
	@echo "${CYAN}Building library!${DEF_COLOR}"
	ar rcs ${NAME} ${OBJS} ${LIBFT_OBJS}  # Link with libft object files
	@echo "${GREEN}${NAME} compiled!${DEF_COLOR}"
	
bonus: fclean ${BONUS_OBJS} ${LIBFT_OBJS}
	@echo "${CYAN}Building ${NAME} in ${RED}BONUS MODE${CYAN}!${DEF_COLOR}"
	make -C ${LIBFTDIR}  # Ensure libft is built
	@echo "${CYAN}Building library in ${RED}BONUS MODE${CYAN}!${DEF_COLOR}"
	ar rcs ${NAME} ${BONUS_OBJS} ${LIBFT_OBJS}  # Link with libft object files
	@echo "${GREEN}${NAME} compiled in ${RED}BONUS MODE${CYAN}!${DEF_COLOR}"
	
clean:
	cd ${LIBFTDIR} && ${MAKE} clean
	@echo "${BLUE}libft object files cleaned!${DEF_COLOR}"
	${RM} ${OBJS} ${BONUS_OBJS}
	${RM} srcs/bonus/*.o
	@echo "${BLUE}ft_printf object files cleaned!${DEF_COLOR}"

fclean: clean
	@cd ${LIBFTDIR} && ${MAKE} fclean
	@echo "${CYAN}libft executable files cleaned!${DEF_COLOR}"
	${RM} ${NAME}
	@echo "${CYAN}ft_printf executable files cleaned!${DEF_COLOR}"
	
re: fclean all

.PHONY: all clean fclean re bonus
