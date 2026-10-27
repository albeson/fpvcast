# fpvcast

Vídeo dos óculos FPV da DJI direto no HDMI, sem celular, sem computador, sem app.

O fpvcast é um pequeno aparelho baseado em Raspberry Pi: você liga o cabo USB dos óculos nele, e o vídeo aparece
na tela. Hoje funciona com o **DJI Goggles N3**.

> "DJI" e os nomes dos óculos são marcas da DJI. O fpvcast é um projeto independente, sem relação com a DJI.

## O que ele faz

- **Vídeo no HDMI** em 1080p30, com baixa latência (medida em ~27 ms só no decodificador).
- **Liga e usa.** Sem celular, sem computador, sem aplicativo — é só o Pi entre os óculos e a TV/monitor.
- **Reconecta sozinho** se o drone desligar e religar, ou se o modo da câmera mudar.
- **Página de configuração** pelo celular ou pelo PC, em `http://fpvcast.local`, sem precisar de internet:
  status do vídeo, Wi-Fi, telas do HDMI e dados do aparelho.
- **Primeiro uso só com o celular:** o aparelho cria sua própria rede Wi-Fi (`fpvcast`) para você configurar a
  rede de casa pela página, lendo um QR code na tela.

## O que você precisa

- Um **Raspberry Pi Zero W** (ou Zero 2 W) e um cartão microSD.
- Os óculos (**DJI Goggles N3**; outros modelos da DJI ainda não foram testados).
- Um adaptador OTG USB-C→USB-A, um cabo USB-A→micro-USB, e uma fonte de alimentação para o Pi.
- Uma licença de uso (veja abaixo).

## Como instalar

1. Baixe a imagem mais recente nos [**Releases**](../../releases/latest) deste repositório
   (`fpvcast-<versão>.img.xz`).
2. Grave no cartão microSD com o [Raspberry Pi Imager](https://www.raspberrypi.com/software/) ou o
   [balenaEtcher](https://etcher.balena.io/), usando "Custom image" / "Flash from file".
3. Coloque o cartão no Pi e ligue. No primeiro boot (leva um pouco mais, ele está se preparando), a tela mostra
   um QR code — leia com o celular para entrar na rede do aparelho e abrir a página de configuração.
4. Cadastre sua rede Wi-Fi pela página (opcional, mas recomendado).
5. Ative a licença pela própria página, na aba Sistema.
6. Ligue os óculos no Pi: adaptador OTG no óculos, cabo USB-A→micro-USB na porta **"USB"** do Pi (a alimentação
   vai separada, na porta "PWR IN"). Nos óculos, deixe **"OTG Wired Connection to Computer" desligado**.

## Licença

Sem uma licença válida para o aparelho, não há vídeo. O fpvcast ainda não tem uma loja automática — para obter
uma licença, abra uma [Issue](../../issues) ou entre em contato.

## Dúvidas e suporte

Abra uma [Issue](../../issues) neste repositório. Ao anexar logs ou capturas de tela, não inclua a senha da sua
rede Wi-Fi.

## Código aberto usado pelo fpvcast

A imagem é construída sobre o Raspberry Pi OS, que inclui o Linux e outros programas sob a licença GPL e
licenças livres semelhantes. O código-fonte desses programas está nas fontes oficiais do Raspberry Pi OS e do
Debian, em [github.com/RPi-Distro](https://github.com/RPi-Distro) e [deb.debian.org](https://deb.debian.org/).
O fpvcast em si (o que roda nos óculos) não é um software livre.
