#
# (C) Copyright 2008
# Wolfgang Denk, DENX Software Engineering, wd@denx.de.
#
# See file CREDITS for list of people who contributed to this
# project.
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License as
# published by the Free Software Foundation; either version 2 of
# the License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.	See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston,
# MA 02111-1307 USA
#

include $(TOPDIR)/config.mk

LIB	:= $(obj)liblogo_disp.o

COBJS-$(CONFIG_SYS_AUTO_DETECT) += logo_disp_read_edid.o
COBJS-$(CONFIG_SYS_LOGO_DISP_NTSC) += logo_disp_525p.o
COBJS-$(CONFIG_SYS_LOGO_DISP_PAL) += logo_disp_625p.o
COBJS-$(CONFIG_SYS_LOGO_DISP_1080P50) += logo_disp_1080p50.o
COBJS-$(CONFIG_SYS_LOGO_DISP_1080P60) += logo_disp_1080p60.o

COBJS	:= $(COBJS-y)
SRCS	:= $(COBJS:.o=.c)
OBJS	:= $(addprefix $(obj),$(COBJS))

EXTRA_CFLAGS += -I$(TOPDIR)/drivers/i2c
CFLAGS += $(EXTRA_CFLAGS)
HOSTCFLAGS += $(EXTRA_CFLAGS)
CPPFLAGS += $(EXTRA_CFLAGS)

all:	$(LIB)

$(LIB):	$(obj).depend $(OBJS)
	$(call cmd_link_o_target, $(OBJS))

#########################################################################

# defines $(obj).depend target
include $(SRCTREE)/rules.mk

sinclude $(obj).depend

#########################################################################
