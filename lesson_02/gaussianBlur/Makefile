#******************************************************************************#
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: troussel <troussel@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2015/01/10 12:59:03 by troussel          #+#    #+#              #
#    Updated: 2015/01/10 21:47:03 by troussel         ###   ########.fr        #
#                                                                              #
#******************************************************************************#
NAME =	HW2

SRCDIR = srcs/
CPPFILES =	main.cpp student_func.cu compare.cpp reference_calc.cpp
SRC = $(addprefix $(SRCDIR), $(CPPFILES))
GPP = nvcc -std=c++11
OBJ = $(SRC:.cpp=.o)
HDDIR = includes/

all: $(NAME)

$(NAME): $(SRC)
		$(GPP) `pkg-config --cflags opencv` -o $(NAME) -I $(HDDIR) $(SRC) `pkg-config --libs opencv`

%.o: %.c
	$(GPP) -c -o $@ $^  -I $(HDDIR)

clean:
		rm -f $(OBJ)

fclean: clean
		rm -rf $(NAME)

re: fclean all

.PHONY: clean fclean re
