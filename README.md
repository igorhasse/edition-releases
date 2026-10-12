# edition: instaladores e atualizações

O **edition** grava as suas partidas de Valorant e transforma as melhores jogadas em edits com cada kill
caindo no kick da música, em 16:9 e 9:16. Tudo roda no seu PC.

O código do app não fica aqui: este repositório só tem as versões.

## Requisitos

- Windows 11 e Valorant.
- [OBS Studio](https://obsproject.com) 30 ou mais novo.
- Placa de vídeo NVIDIA, AMD ou Intel com codificador de vídeo. Sem ela, o edit sai pela CPU, só que
  mais devagar.

## Instalar

1. Em [Releases](../../releases/latest), baixe **win-x64-edition-Setup.zip** e extraia a pasta inteira.
   O instalador precisa da pasta `.installer` ao lado dele.
2. Rode **edition-Setup.exe**. Se o Windows avisar que protegeu o computador, clique em *Mais
   informações* e depois em *Executar assim mesmo*. O app ainda não tem assinatura digital.
3. O edition abre e fica na bandeja, ao lado do relógio: clique duplo abre o app, e o botão direito
   mostra o menu.

O app se atualiza sozinho. Quando uma versão nova estiver pronta, aparece **Reiniciar e atualizar** no
menu da bandeja.

## Configurar o OBS

O edition comanda o OBS: ele começa a gravar quando a partida começa e para quando ela acaba.

1. **Ferramentas → Configurações do servidor WebSocket:** marque *Ativar servidor WebSocket*. A senha
   pode ficar como está, porque o edition lê sozinho.
2. **Uma cena com a Captura de jogo** do Valorant. Se quiser o som do jogo separado da música e do
   microfone, crie também uma *Captura de áudio de aplicativo* do Valorant e mande essa fonte só para a
   faixa 2 (*Propriedades avançadas de áudio*).
3. **Configurações → Vídeo:** resolução 1920×1080. Use o maior FPS que o seu PC aguentar sem perder
   quadros: 240 deixa o motion blur do edit mais bonito, mas 120 e 60 também funcionam.
4. **Configurações → Saída**, no modo **Avançado**, aba **Gravação:**
   - caminho da gravação: a pasta **Vídeos**, que é onde o edition procura as partidas;
   - formato: **MP4 Híbrido**;
   - faixas de áudio: **1 e 2**;
   - codificador: o da sua placa (NVIDIA NVENC AV1 ou HEVC, AMD AMF ou Intel QuickSync);
   - controle de taxa: **CQP**, nível **18**, e quadro-chave a cada **1 s**.
5. Rode o OBS como administrador, para ele não perder quadros quando o jogo puxar a placa.

## Usar

1. Abra o edition, o OBS e o Valorant, e jogue. A gravação automática começa e termina sozinha. No fim
   da partida, o edition baixa as suas kills e acha o quadro exato de cada uma no vídeo.
2. Em **Partidas**, escolha as jogadas com *Pôr no edit*.
3. Em **Montar edit**, escolha a música (um arquivo ou um link do YouTube), o kick onde entra a primeira
   kill, o formato e o estilo. Depois clique em **Gerar edit**.
4. Quando o edit fica pronto, chega uma notificação. Os vídeos ficam em `Vídeos\edition\edits`.
