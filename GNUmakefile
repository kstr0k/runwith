APP := runwith
PKG := $(APP)

ifeq ($(file <mk/boilerplate.mk),)
$(info Initializing submodules...)
$(shell git submodule update std-mk >&2)
endif
include mk/shell-is-bash-one.mk
include mk/boilerplate.mk
include mk/cmdline-app.mk
include mk/sh-app.mk

all: patch_self

patch_self:
	./runwith patch_builtins
.PHONY: patch_self

release: all
	VERSION='$(VERSION)' mk/gh-release-me
