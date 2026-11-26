DOTNET := $(if $(wildcard $(HOME)/.dotnet9/sdk/dotnet),$(HOME)/.dotnet9/sdk/dotnet,dotnet)
SOLUTION := chess/Chess.sln
PROJECT := chess/Chess/Chess.csproj
DOTNET_INSTALL_DIR := $(HOME)/.dotnet9/sdk
DOTNET_INSTALL_SCRIPT := $(HOME)/.dotnet9/dotnet-install.sh

.PHONY: deps build run clean fmt

deps:
	mkdir -p "$(HOME)/.dotnet9"
	curl -fsSL https://dot.net/v1/dotnet-install.sh -o "$(DOTNET_INSTALL_SCRIPT)"
	bash "$(DOTNET_INSTALL_SCRIPT)" --channel 9.0 --install-dir "$(DOTNET_INSTALL_DIR)"

build:
	"$(DOTNET)" build "$(SOLUTION)"

run:
	"$(DOTNET)" run --project "$(PROJECT)"

clean:
	"$(DOTNET)" clean "$(SOLUTION)"

fmt:
	"$(DOTNET)" format "$(SOLUTION)"
