dnl Process this file with autoconf to produce a configure script.

AC_INIT([M68000 CPU],[1.0],[Christian.Bauer@uni-mainz.de],[M68000CPU])

AC_CONFIG_SRCDIR(gencpu.c)

AC_PREREQ([2.71])
AC_CONFIG_HEADERS([config.h])

dnl Aliases for PACKAGE and VERSION macros.
AC_DEFINE_UNQUOTED(PACKAGE, "$PACKAGE_NAME", [Define this program name.])
AC_DEFINE_UNQUOTED(VERSION, "$PACKAGE_VERSION", [Define this program version.])

dnl Canonical system information.
AC_CANONICAL_HOST
AC_CANONICAL_TARGET

dnl Target CPU type.
HAVE_I386=no
HAVE_POWERPC=no
HAVE_X86_64=no
case "$target_cpu" in
  i386* | i486* | i586* | i686* | i786* ) HAVE_I386=yes;;
  powerpc* ) HAVE_POWERPC=yes;;
  x86_64* ) HAVE_X86_64=yes;;
esac

dnl Checks for programs.
AC_PROG_CC
AC_PROG_CC_C_O
AC_PROG_CPP
AC_PROG_CXX
AX_PROG_CC_FOR_BUILD
AX_PROG_CXX_FOR_BUILD
AC_PROG_MAKE_SET
AC_PROG_EGREP
AC_PROG_LN_S

dnl Checks for typedefs, structures, and compiler characteristics.
AC_C_BIGENDIAN
AC_C_CONST
AC_C_INLINE
AC_CHECK_SIZEOF(short, 2)
AC_CHECK_SIZEOF(int, 4)
AC_CHECK_SIZEOF(long, 4)
AC_CHECK_SIZEOF(long long, 8)
AC_CHECK_SIZEOF(float, 4)
AC_CHECK_SIZEOF(double, 8)
AC_CHECK_SIZEOF(long double, 12)
AC_CHECK_SIZEOF(void *, 4)
AC_TYPE_OFF_T
AC_CHECK_TYPES(loff_t)
AC_CHECK_TYPES(caddr_t)
AC_TYPE_SIZE_T

dnl Checks for library functions.
AC_CHECK_FUNCS(strdup strerror)



dnl Generate Makefile.
AC_SUBST(DEFINES)
AC_CONFIG_FILES([Makefile])
AC_OUTPUT


