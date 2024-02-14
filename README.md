# Servidor Multi Streaming

Este projeto fornece um servidor simples para fazer live e transmitir para mais de uma plataforma simultaneamente, implementado utilizando NGINX com suporte aos protocolos RTMP (Real Time Message Protocol)
Um simples servidor  ✨ Este projeto é compatível apenas com ingests que utilizam o protocolo RTMP.

## Desenvolvimento

Este projeto foi desenvolvido pela Lais Lima em seu canal do YouTube. O vídeo pode ser acessado [aqui](https://youtu.be/1FJYPwEKx_I?si=WJ4ar1LCD5lKgRGw).

## Requisitos

- [Docker](https://www.docker.com/)
- [OBS](https://obsproject.com/pt-br/download)
- Conta no [YouTube](https://www.youtube.com/)
- Conta na [Twitch](https://www.twitch.tv/)

## Tecnologias Utilizadas

- Docker Compose
- NGINX

## Protocolos Suportados

- RTMP (Real Time Message Protocol)

## Como Executar

1. **Configuração do YouTube:**
   - Vá ao seu canal do YouTube e preencha as variáveis do arquivo `.env` com a URL e a Chave de transmissão:

     ```dotenv
     YOUTUBE_STREAMING_URL=rtmp://youtube.com/xxxxxx
     YOUTUBE_STREAMING_KEY=1234567890abcdefg
     ```

2. **Configuração da Twitch:**
   - Vá ao seu canal da Twitch e preencha as variáveis do arquivo `.env` com a Chave de transmissão e a URL de transmissão:

     ```dotenv
     TWITCH_STREAMING_URL=rtmp://sao03.contribute.live-video.net/app
     TWITCH_STREAMING_KEY=1234567890abcdefg
     ```

3. **Subir o Container:**
   - Suba o container da aplicação utilizando o Docker Compose:

     ```bash
     docker-compose up --build
     ```

4. **Configuração no OBS:**
   - Abra o OBS e vá para Configurações > Transmissão > Servidor:

     ```
     rtmp://localhost:1935/live
     ```

   - Clique em "OK" e, em seguida, clique em "Iniciar transmissão".

Este servidor permite transmitir para as plataformas configuradas simultaneamente, proporcionando uma solução simples para streaming multiplataforma. Certifique-se de configurar corretamente as variáveis de ambiente no arquivo `.env` antes de iniciar a transmissão.
