---
title: Solução de problemas de transmissão ao vivo no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo discutirá as opções de solução de problemas para eventos de streaming do Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767915"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Solução de problemas de eventos ao vivo no Microsoft Teams

> [!IMPORTANT]
> **China**: os usuários localizados na China não poderão configurar ou participar de eventos ao vivo do Teams ou do Yammer ou exibir vídeos sob demanda porque, atualmente, a CDN do Azure, com a qual esses aplicativos dependem, pode não estar acessível na China.
>
> Como administrador, talvez seja necessário configurar uma VPN para conectar sua rede corporativa para que esses aplicativos funcionem perfeitamente. Depois de concluído, as pessoas na sua organização poderão agendar e participar de eventos ao vivo.

## <a name="before-a-live-event"></a>Antes de um evento ao vivo

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>Verifique se todos os eventos são acessíveis em sua rede

#### <a name="general-teams-endpoints"></a>Pontos de extremidade do General Teams

O Teams requer conectividade com a Internet. Todos os pontos de extremidade listados em [Office 365 pontos de extremidade do Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) precisam ser acessíveis pelos usuários do Teams na rede da sua organização.

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Eventos ao vivo do Codificador do Teams – pontos de extremidade de ingestão RMTP

Para obter um feed de vídeo para um evento ao vivo do Teams Encoder enviado ao Teams do codificador, você precisará do nome do domínio e das portas abertas no firewall da rede:

- Domínios: *.rtmpingest.mcr.teams.microsoft.com
- Portas: 1935/1936 (para RTMP/RTMPS)

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>Verifique se você tem largura de banda de carregamento suficiente

Ao produzir ou transmitir um evento ao vivo por meio do RTMP, é possível que a largura de banda de carregamento da Internet no site que envia push da transmissão ao vivo possa não ser suficiente. A baixa largura de banda de upload pode resultar em quadros ou problemas descartados no próprio vídeo ao vivo, o que pode resultar em problemas de reprodução para os espectadores.

Verifique se a velocidade de carregamento do computador e da rede que empurra a transmissão ao vivo é maior do que a taxa de bits definida para a transmissão ao vivo. Se você estiver gerando um fluxo de 5 Mbps do codificador, mas sua taxa de bits de carregamento estiver próxima ou inferior a isso, você poderá encontrar problemas para não poder carregar seu fluxo rápido o suficiente.

Se você tiver problemas de largura de banda de upload, aqui estão algumas coisas que você pode tentar:

1. Use uma conexão ethernet com fio rígido para qualquer computador do qual você esteja empurrando o fluxo para evitar quedas no Wi-Fi.
1. Reduza a taxa de bits de codificação do feed ao vivo para um valor bem abaixo da velocidade máxima de carregamento.

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>Preparando sua rede para muitos espectadores simultâneos

Durante eventos ao vivo, muitas pessoas se juntarão para assistir ao seu evento ao vivo. Isso pode colocar uma pressão sobre sua rede e largura de banda de download da Internet. Você precisa avaliar sua infraestrutura de rede atual e garantir que as pessoas em sua rede corporativa tenham a largura de banda necessária para assistir a um evento ao vivo. Para ajudar a reduzir o tráfego da Internet necessário para eventos ao vivo, há duas opções:

1. Configure proxies de cache existentes em sua rede para armazenar em cache vídeos do Teams.
1. Use uma solução de entrega de vídeo eCDN de terceiros para otimizar o tráfego de vídeo.

### <a name="i-cant-create-a-live-event"></a>Não consigo criar um evento ao vivo

Há permissões no Microsoft Teams e no Yammer de que um usuário precisa ser capaz de criar um evento ao vivo, dependendo de qual serviço você está usando para o evento ao vivo.

1. Verifique se o administrador do Teams permitiu que você criasse eventos ao vivo.
1. Verifique com o administrador se você tem uma licença válida do Teams que permite a criação de eventos ao vivo.

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>Verifique se os espectadores têm permissão para assistir ao evento

Os eventos ao vivo do Microsoft Teams têm algumas funções diferentes para permissões no próprio evento (Organizador, Produtor, Apresentador, Participante).

Consulte [funções de grupo de eventos do Microsoft Teams](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) para obter mais informações.

## <a name="producing-a-live-event"></a>Produzindo um evento ao vivo

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>Não sei como configurar meu codificador

A maneira mais fácil de começar é seguir as instruções descritas no artigo [Usando um codificador para transmissão ao vivo no Microsoft Teams](teams-encoder-setup.md) .

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>Meu codificador não está se conectando à URL de ingestão de servidor

- Verifique se a URL RTMP foi inserida corretamente como a saída do codificador.
- Verifique se a chave RTMP é inserida corretamente como a saída do codificador.
- Verifique o status da conexão com a Internet para garantir que o codificador esteja conectado e online corretamente.
- Você pode ter configurações relacionadas à segurança de rede ou firewall que podem estar bloqueando a saída de sua conexão.
- Seu codificador pode não ter suporte com o Teams. Confira a lista de codificadores testados em [Usando um codificador para transmissão ao vivo no Microsoft Teams](teams-encoder-setup.md).

### <a name="i-cant-get-rtmps-to-work"></a>Não consigo fazer os RTMPs funcionarem

- Alguns codificadores podem dar suporte a uma implementação diferente que não tenha suporte do Teams. Confira a lista de codificadores testados que funcionam com o Teams em [Usar um codificador para transmissão ao vivo no Microsoft Teams](teams-encoder-setup.md).
- Nem todos os codificadores ou versões dão suporte a RTMPs. Verifique com o fabricante ou o criador de software para ver o que eles dão suporte.

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>Eu tentei começar a configurar e está demorando muito

Em geral, pode levar alguns minutos para que a configuração seja executada antes que você possa começar a pressionar o codificador. É possível que o serviço esteja ocupado que isso possa levar mais tempo para começar, portanto, é recomendável que você dê tempo suficiente para iniciar a instalação antes do evento ao vivo agendado.

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>Tentei começar a configurar, mas há muitos eventos acontecendo

Se você receber uma mensagem ao iniciar um evento em que o número máximo de eventos foi atingido, entre em contato com um administrador do Teams, que tem a capacidade de parar outros eventos para abrir espaço para um evento de maior prioridade.

### <a name="i-cant-see-producer-view"></a>Não consigo ver a exibição do produtor

1. Pode levar alguns segundos para que a versão prévia do produtor apareça depois que você começar a transmitir do codificador.
1. Verifique se o codificador está conectado ao Teams.
1. Às vezes, pode ajudar a atualizar a página no Teams. Você pode ser perguntado se deseja sair da página; isso não afetará seu evento ao vivo.
1. Algumas redes podem bloquear o acesso ao conteúdo. Verifique se as configurações de segurança de rede e firewall permitem que o protocolo RTMP e os [domínios necessários](/microsoft-365/enterprise/urls-and-ip-address-ranges) estejam na lista permitida. Ele pode ajudar a tentar ver se ele funciona em um ambiente de rede diferente, independente de uma rede corporativa, VPN ou rede bloqueada.

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>Meu feed parece ruim, tem má qualidade, ou é defeituoso

1. Verifique a largura de banda de upload do computador do qual você está empurrando a transmissão ao vivo. A baixa largura de banda pode causar quadros descartados, má qualidade ou um fluxo de vídeo com aparência de falha. Você precisa de uma largura de banda de upload que seja maior do que a taxa de bits em que você está transmitindo.
1. Verifique se você está usando as configurações recomendadas do codificador para o Teams. Consulte [Configurar codificadores manualmente para transmissão de eventos ao vivo no Microsoft Teams](teams-encoder-configuration.md) para obter mais informações.
1. Verifique se o áudio/vídeo que entra no codificador não tem problemas. Os feeds de áudio ou vídeo de origem roteado para o codificador podem ter problemas em si, o que resultaria em uma experiência ruim enviada aos espectadores.
1. Verifique a carga da CPU no codificador. Você pode estar maximizando sua CPU com o conteúdo de origem e/ou com a taxa de bits que está tentando pressionar. Se a carga da CPU for muito alta, tente reduzir a complexidade de suas sobreposições/conteúdo de feed ao vivo ou reduza a taxa de bit em que você está transmitindo.
1. Verifique se o codificador está atualizado. Se for um codificador de hardware, verifique se você tem as atualizações de firmware mais recentes. Se for um codificador de software, verifique se você está executando a versão mais recente.
1. Tente redefinir ou reiniciar seu codificador. Observe que, se você fizer isso durante uma transmissão ao vivo, seus espectadores verão um erro durante a reprodução enquanto o codificador estiver sendo reiniciado. Depois de reiniciar a transmissão ao vivo do codificador, os espectadores terão que recarregar a página para obter a transmissão ao vivo novamente.

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>Terminei meu evento ao vivo do meu codificador, mas os espectadores estão vendo um erro

Selecione **Parar evento** antes de desconectar seu codificador. Se você já desconectou o codificador, ainda poderá selecionar **Parar evento**, mas os espectadores poderão ver um erro.

### <a name="my-viewers-are-seeing-issues"></a>Meus telespectadores estão vendo problemas

- Se um único visualizador estiver relatando um problema, verifique se o visualizador tem largura de banda suficiente e está em uma boa conexão com a Internet para assistir ao evento.
- Se várias pessoas na mesma rede estiverem tendo problemas, você poderá estar enfrentando problemas relacionados ao congestionamento de rede. Examine [Dimensionar a entrega de vídeo e monitore o tráfego de rede usando eCDNs com o Microsoft Teams](teams-stream-ecdn.md) para ver se você pode identificar uma solução para o seu problema.
- Muitas vezes, quando vários espectadores estão vendo um problema, ele realmente está relacionado ao feed do codificador.
  - Verifique se o codificador está definido corretamente para as especificações descritas na configuração do codificador e configurado corretamente.
  - Verifique se você tem largura de banda de carregamento suficiente para transmitir. Você pode tentar reduzir a largura de banda da saída do codificador.
  - Às vezes, a redefinição do codificador ajuda, mas observe que você deve manter as mesmas configurações quando reconectado. Os membros da audiência podem ver um erro ou uma falha no evento ao vivo.

### <a name="i-or-my-viewers-cant-hear-the-video"></a>Eu, ou meus telespectadores, não consigo ouvir o vídeo

1. Verifique se o codificador está enviando áudio.
1. Verifique se o dispositivo de áudio está conectado.
1. Se estiver no Windows, verifique se o dispositivo de áudio correto está selecionado e desmutado.
1. Se houve uma interrupção do codificador, alguns navegadores ou dispositivos podem não ser capazes de recuperar e reproduzir o áudio corretamente.

> [!NOTE]
> Se você implantou o Microsoft eCDN como provedor de distribuição de vídeo para eventos ao vivo, consulte [Solucionar problemas de desempenho do eCDN](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) para obter mais detalhes sobre como solucionar problemas de desempenho do eCDN que você pode estar enfrentando.
