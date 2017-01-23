	#include <stdio.h>
	#include <stdarg.h> // va_list, func va_start, va_arg, va_end
	#include <libft.h>
	#include <stdlib.h>
	#include <ft_printf.h>
	#include <limits.h>

	void	debug_print_struct_data(t_box *box)
	{
		//Begin Debug Code
		printf("---STRUCT  DATA  BEGIN ---\n");
		printf("pound:%d, ", box->pound_flag);
		printf("zero :%d, ", box->zero_flag);
		printf("minus:%d, ", box->minus_flag);
		printf("space:%d, ", box->space_flag);
		printf("plus :%d\n", box->plus_flag);
		printf("field_width:%d\n", box->field_width);
		printf("precision:%d\n", box->precision);
		printf("len_modifier:%d\n", box->len_modifier);
		printf("specifier:%d\n", box->specifier);
		printf("box->len_value:%d\n", box->len_value);
		printf("---STRUCT  DATA  END   ---\n");
		// End Debug Code
	}

	void	debug_d_i_ints()
	{
		char *format = "one:%5d\ntwo:%5d\n";
		int val;

		printf("--- BEGIN DEBUG_D_I_INTS() ---\n");

		val = ft_printf(format, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format, 42, -1234567890123);
		printf("val:%d\n", val);


		printf("\n");

		val = ft_printf(format, 42, 12345);
		printf("val:%d\n", val);
		val = printf(format, 42, 12345);
		printf("val:%d\n", val);


		printf("\n");

		val = ft_printf(format, -1, -1);
		printf("val:%d\n", val);
		val = printf(format, -1, -1);
		printf("val:%d\n", val);


		printf("\n");

		val = ft_printf(format, 0, 1);
		printf("val:%d\n", val);
		val = printf(format, 0, 1);
		printf("val:%d\n", val);


		printf("\n");

		val = ft_printf(format, -0, 1);
		printf("val:%d\n", val);
		val = printf(format, -0, 1);
		printf("val:%d\n", val);


		//printf("%s", ft_big_itoa(1234567890123));

		//wow, casts it as a long so it look like a big number,
		//i'm right by accident / design
		//printf("%10lld\n", -42);
		//val = printf(format, -42, 12345);
		//:set paste
		//:set nopaste

	}

	void	debug_d_i_len_mod()
	{
		char *format0 = "one:%5d\ntwo:%5d\n";
		char *format1 = "one:%5hhd\ntwo:%5hhd\n";
		char *format2 = "one:%5hd\ntwo:%5hd\n";
		char *format3 = "one:%5ld\ntwo:%5ld\n";
		char *format4 = "one:%5lld\ntwo:%5lld\n";
		char *format5 = "one:%5jd\ntwo:%5jd\n";
		char *format6 = "one:%5td\ntwo:%5td\n";
		char *format7 = "one:%5zd\ntwo:%5zd\n";
		int val;

		printf("--- BEGIN DEBUG_D_I_LEN_MOD() ---\n");

		val = ft_printf(format0, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format0, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format1, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format1, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format2, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format2, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format3, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format3, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format4, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format4, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format5, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format5, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format6, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format6, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");

		val = ft_printf(format7, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format7, 42, -1234567890123);
		printf("val:%d\n", val);

		printf("\n");
	}

	void	debug_d_i_precision()
	{
		char *format0 = "one:%5.-10d\ntwo:%5.-10d\n";
		char *format1 = "one:%5.5hhd\ntwo:%5.5hhd\n";
		char *format2 = "one:%3.3hd\ntwo:%3.3hd\n";
		char *format3 = "one:%.0ld\ntwo:%.0ld\n";
		char *format4 = "one:%.10lld\ntwo:%5lld\n";
		char *format5 = "one:%.3jd\ntwo:%5jd\n";
		char *format6 = "one:%.7td\ntwo:%5td\n";
		char *format7 = "one:%.7zd\ntwo:%5zd\n";
		int val;

		printf("--- BEGIN DEBUG_D_I_PRECISION() ---\n");

		val = ft_printf(format0, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format0, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format1, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format1, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format2, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format2, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format3, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format3, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format4, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format4, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format5, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format5, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format6, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format6, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

		val = ft_printf(format7, 42, -1234567890123);
		printf("val:%d\n", val);
		val = printf(format7, 42, -1234567890123);
		printf("val:%d\n", val);
		printf("\n");

	}


	void	debug_d_i_space()
	{
		char *format0 = "one:%5.d:\n";
		char *format1 = "one:%d:\n";
		char *format2 = "one:% .d:\n";
		char *format3 = "one:% .0ld:\n";
		char *format4 = "one:% .10lld:\n";
		char *format5 = "one:% .3jd:\n";
		char *format6 = "one:% .7d:\n";
		char *format7 = "one:% .7zd:\n";
		int val;
		int space_one;

		printf("--- BEGIN DEBUG_D_I_SPACE() ---\n");
		space_one = 0;

		printf("FORMAT STRING 0, PRINT 0\n");
		val = ft_printf(format0, space_one);
		printf("val:%d\n", val);
		val = printf(format0, space_one);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 0, PRINT 1\n");
		val = ft_printf(format0, space_one + 1);
		printf("val:%d\n", val);
		val = printf(format0, space_one + 1);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 0, PRINT -1\n");
		val = ft_printf(format0, space_one - 1);
		printf("val:%d\n", val);
		val = printf(format0, space_one - 1);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 1, PRINT 0\n");
		val = ft_printf(format1, (space_one));
		printf("val:%d\n", val);
		val = printf(format1, (space_one));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 2, PRINT 0\n");
		val = ft_printf(format2, (space_one));
		printf("val:%d\n", val);
		val = printf(format2, (space_one));
		printf("val:%d\n\n", val);


		printf("FORMAT STRING 2\n");
		val = ft_printf(format2, (space_one + 1));
		printf("val:%d\n", val);
		val = printf(format2, (space_one + 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 3\n");
		val = ft_printf(format3, (space_one));
		printf("val:%d\n", val);
		val = printf(format3, (space_one));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 4\n");
		val = ft_printf(format4, (space_one - 1));
		printf("val:%d\n", val);
		val = printf(format4, (space_one - 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 5\n");
		val = ft_printf(format5, (space_one + 1));
		printf("val:%d\n", val);
		val = printf(format5, (space_one + 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 6\n");
		val = ft_printf(format6, (space_one - 1));
		printf("val:%d\n", val);
		val = printf(format6, (space_one - 1));
		printf("val:%d\n\n", val);
	}

	void	debug_d_i_plus()
	{
		char *format0 = "one:%+ 5.d:\n";
		char *format1 = "one:%+ d:\n";
		char *format2 = "one:%+ .d:\n";
		char *format3 = "one:%+ .0ld:\n";
		char *format4 = "one:%+ .10lld:\n";
		char *format5 = "one:%+ .3jd:\n";
		char *format6 = "one:%+ .7d:\n";
		char *format7 = "one:%+ .7zd:\n";
		int val;
		int space_one;

		printf("--- BEGIN DEBUG_D_I_PLUS() ---\n");
		space_one = 0;

		printf("FORMAT STRING 0, PRINT 0\n");
		val = ft_printf(format0, space_one);
		printf("val:%d\n", val);
		val = printf(format0, space_one);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 0, PRINT 1\n");
		val = ft_printf(format0, space_one + 1);
		printf("val:%d\n", val);
		val = printf(format0, space_one + 1);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 0, PRINT -1\n");
		val = ft_printf(format0, space_one - 1);
		printf("val:%d\n", val);
		val = printf(format0, space_one - 1);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 1, PRINT 0\n");
		val = ft_printf(format1, (space_one));
		printf("val:%d\n", val);
		val = printf(format1, (space_one));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 2, PRINT 0\n");
		val = ft_printf(format2, (space_one));
		printf("val:%d\n", val);
		val = printf(format2, (space_one));
		printf("val:%d\n\n", val);


		printf("FORMAT STRING 2\n");
		val = ft_printf(format2, (space_one + 1));
		printf("val:%d\n", val);
		val = printf(format2, (space_one + 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 3\n");
		val = ft_printf(format3, (space_one));
		printf("val:%d\n", val);
		val = printf(format3, (space_one));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 4\n");
		val = ft_printf(format4, (space_one - 1));
		printf("val:%d\n", val);
		val = printf(format4, (space_one - 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 5\n");
		val = ft_printf(format5, (space_one + 1));
		printf("val:%d\n", val);
		val = printf(format5, (space_one + 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 6\n");
		val = ft_printf(format6, (space_one - 1));
		printf("val:%d\n", val);
		val = printf(format6, (space_one - 1));
		printf("val:%d\n\n", val);
	}

	void	debug_d_i_pound()
	{
		char *format0 = "one:%#+ 5.d:\n";
		char *format1 = "one:%#+ d:\n";
		char *format2 = "one:%#+ .d:\n";
		char *format3 = "one:%#+ .0ld:\n";
		char *format4 = "one:%#+ .10lld:\n";
		char *format5 = "one:%#+ .3jd:\n";
		char *format6 = "one:%#+ .7d:\n";
		char *format7 = "one:%#+ .7zd:\n";
		int val;
		int space_one;

		printf("--- BEGIN DEBUG_D_I_SPACE() ---\n");
		space_one = 0;

		printf("FORMAT STRING 0, PRINT 0\n");
		val = ft_printf(format0, space_one);
		printf("val:%d\n", val);
		val = printf(format0, space_one);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 0, PRINT 1\n");
		val = ft_printf(format0, space_one + 1);
		printf("val:%d\n", val);
		val = printf(format0, space_one + 1);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 0, PRINT -1\n");
		val = ft_printf(format0, space_one - 1);
		printf("val:%d\n", val);
		val = printf(format0, space_one - 1);
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 1, PRINT 0\n");
		val = ft_printf(format1, (space_one));
		printf("val:%d\n", val);
		val = printf(format1, (space_one));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 2, PRINT 0\n");
		val = ft_printf(format2, (space_one));
		printf("val:%d\n", val);
		val = printf(format2, (space_one));
		printf("val:%d\n\n", val);


		printf("FORMAT STRING 2\n");
		val = ft_printf(format2, (space_one + 1));
		printf("val:%d\n", val);
		val = printf(format2, (space_one + 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 3\n");
		val = ft_printf(format3, (space_one));
		printf("val:%d\n", val);
		val = printf(format3, (space_one));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 4\n");
		val = ft_printf(format4, (space_one - 1));
		printf("val:%d\n", val);
		val = printf(format4, (space_one - 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 5\n");
		val = ft_printf(format5, (space_one + 1));
		printf("val:%d\n", val);
		val = printf(format5, (space_one + 1));
		printf("val:%d\n\n", val);

		printf("FORMAT STRING 6\n");
		val = ft_printf(format6, (space_one - 1));
		printf("val:%d\n", val);
		val = printf(format6, (space_one - 1));
		printf("val:%d\n\n", val);
	}



















