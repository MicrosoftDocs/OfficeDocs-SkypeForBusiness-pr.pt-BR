---
title: Dimensionar a entrega de vídeo no Microsoft Teams
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
description: Este artigo discutirá a distribuição de vídeo em escala e as eCDNs (redes de entrega de conteúdo empresarial) para eventos de streaming do Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767911"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>Dimensionar a entrega de vídeo e monitorar o tráfego de rede usando eCDNs com o Microsoft Teams

A reprodução de vídeos do Microsoft Teams e eventos ao vivo "Aplicativo externo ou dispositivo" (anteriormente conhecido como produções "Codificador Externo") usam o streaming de bits adaptável (ABR) entregue como um fluxo unicast. Isso significa que cada visualizador está recebendo seu próprio fluxo de vídeo da Internet. Para eventos ou vídeos ao vivo enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de rede e internet consumida pelos espectadores.

As organizações podem querer entender e reduzir esse tráfego de rede para eventos ao vivo e vídeos populares. Nesse caso, o Teams pode ser habilitado para integrar-se a parceiros confiáveis da Microsoft que oferecem soluções de eCDN (rede de distribuição de conteúdo empresarial) que incluem tecnologias de entrega autogerenciada, monitoramento em tempo real e análise detalhada de rede. Essas plataformas eCDN permitem que as organizações monitorem, dimensionem e otimizem a distribuição de fluxos de vídeo (e às vezes outros tipos de conteúdo) em sua rede corporativa.

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>Adquirir e configurar sua solução eCDN fora do Teams

Obtenha ajuda de especialistas para monitorar e escalar a entrega de vídeo, unindo-se a parceiros confiáveis do Microsoft eCDN.

Antes de habilitar uma solução eCDN a ser usada com o Teams, você deve comprar e configurar essa solução eCDN fora e separada do Teams. Para garantir que a solução atenda às suas necessidades, alguns parceiros fornecem avaliações gratuitas de suas tecnologias de entrega de conteúdo e análise de rede.

Várias soluções eCDN são pré-integradas e podem ser habilitadas para uso com o Teams. Confira as informações dos provedores abaixo.

### <a name="hive-streaming"></a>Hive Streaming

A **Plataforma de Experiência de Vídeo de Streaming do Hive** é composta por três produtos principais:

- **A Otimização de Vídeo do Hive** baseia-se em um algoritmo de configuração zero somente software patenteado. A otimização maximiza automaticamente a qualidade e o alcance do VOD (vídeo ao vivo e sob demanda) para toda a organização.
- O **Hive Video Analytics** ajuda os clientes a entender as tendências em eventos ao vivo e no desempenho de vídeo sob demanda para melhorar o envolvimento do visualizador ao longo do tempo. À medida que o engajamento melhora, a adoção de vídeo em toda a empresa também melhora.
- **O Hive Video Operations** fornece recursos poderosos com o objetivo de garantir proativamente o sucesso do streaming de vídeo antes e durante eventos de vídeo ao vivo. As ferramentas operacionais capacitam suas equipes de streaming de vídeo e UC para encontrar e corrigir problemas antes que eles aconteçam.

Todos eles trabalham para criar experiências de vídeo de escopo completo, desde planejamento até execução e análise. Maximizar a experiência de comunicação de vídeo por streaming é crucial para o envolvimento e o alinhamento dos funcionários em sua missão de empresa. Para saber mais, confira [este link](https://www.hivestreaming.com/partners/microsoft).

### <a name="kollective"></a>Kollective

**A Tecnologia Kollective** é uma plataforma de distribuição de conteúdo baseada em nuvem que utiliza emparelhamento inteligente para fornecer vídeo corporativo ao vivo e sob demanda, fornecendo 100% de qualidade de vídeo e 100% de engajamento em apenas 1% da largura de banda. A integração do Kollective com o Teams Live Events permite que funcionários dispersos globalmente consumam vídeo facilmente, melhorando a comunicação dos funcionários, aumentando o envolvimento geral e aumentando as oportunidades de treinamento e retenção.

**O QI do Kollective** é uma plataforma de análise sofisticada e amigável ao usuário para Microsoft Stream. Com relatórios personalizáveis, visualizações e painéis, é fácil quantificar e digerir a experiência e o envolvimento do usuário em redes empresariais globais complexas. Os Gerentes de Comunicação e os Administradores de Rede podem assistir a eventos e atividades de rede em tempo real, para que os gargalos possam ser resolvidos rapidamente, garantindo o pico de desempenho da rede.

Para saber mais sobre essas opções, confira [este link](https://kollective.com/microsoft-live-events/).

### <a name="microsoft-ecdn"></a>Microsoft eCDN

O **Microsoft eCDN** resolve o problema de congestionamento de rede que ocorre durante grandes eventos virtuais corporativos, como reuniões de todas as mãos. O Microsoft eCDN forma uma rede de malha sobre a LAN que reduz a carga em 95% e elimina problemas de rede. O Microsoft eCDN é o primeiro eCDN a usar o WebRTC como sua base, o que significa que nenhuma instalação de software ou hardware é necessária. Os clientes da Fortune 500 atenuam problemas de rede e confiam no Peer5 para seus maiores eventos corporativos.

- A configuração de rede de configuração zero para o Microsoft eCDN garante que os trabalhadores remotos e/ou o tráfego de vídeo pesado não esforcem sua rede nem o obrigam a investir em infraestrutura dispendiosa. Ele inclui detecção automática de site, detecção automática de VPN e travessia automática nat/firewall. Saiba mais [neste link](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant).
- O Teste Silencioso com o Microsoft eCDN permite que os administradores de TI simulem grandes eventos ao vivo em sua rede corporativa, permitindo testes completos e não disruptivos e solução de problemas antes de um evento real. Saiba mais [neste link](/ecdn/how-to/perform-silent-test).
- A análise líder do setor da Microsoft eCDN fornece análises granulares e permite que os administradores encontrem rapidamente a causa raiz de qualquer problema de streaming. Seu kit de ferramentas inclui métricas de entrega e UX, drilldowns avançados, análise por usuário e uma API de back-end. Saiba mais [neste link](/ecdn/technical-documentation/analytics).

### <a name="ramp"></a>Ramp

**O ramp eCDN** reduz o consumo de largura de banda de rede em 90% ou mais ao transmitir eventos ao vivo e vídeo sob demanda (VOD). Use o Ramp para misturar e corresponder a qualquer combinação de tecnologias eCDN— rede multicast, cache e ponto a ponto. Com gerenciamento centralizado, monitoramento e análise perspicaz, você ganha visibilidade e controle sobre o desempenho da rede para criar a experiência de visualizador de maior qualidade.

- **O Ramp Multicast+** é a maneira mais eficiente de transmitir vídeo ao vivo. Usando o protocolo multicast, você só consome a largura de banda necessária para um visualizador, se você tiver 100, 10.000 ou 100.000 espectadores. Saiba mais [neste link](https://www.rampecdn.com/altitudecdn/multicast/).
- **O Ramp OmniCache™** é um software de cache específico para vídeo que usa caches locais para servir vídeos de VOD e ao vivo para públicos próximos, reduzindo drasticamente o número de fluxos de vídeo que viajam por suas conexões de Internet e links de WAN. Saiba mais [neste link](https://www.rampecdn.com/altitudecdn/video-cache/).
- **O P2P (Ramp Peer-to-Peer)** permite otimizar a largura de banda mesmo em locais com infraestrutura limitada. O P2P cria uma rede par de dispositivos cliente que assistem ao mesmo conteúdo para redistribuir os fluxos de vídeo de um dispositivo de exibição para outro. Saiba mais [neste link](https://www.rampecdn.com/altitudecdn/p2p/).

### <a name="riverbed"></a>Riverbed

**Riverbed**, o padrão do setor na otimização de rede, estendeu suas soluções de aceleração para o Teams. Os clientes do Microsoft 365 podem acelerar com confiança o tráfego do Microsoft 365, incluindo o Teams, juntamente com uma riqueza de outros serviços saaS empresariais líderes para aumentar a produtividade da força de trabalho de qualquer lugar. A aceleração do Teams pode ser habilitada por meio de uma configuração sem esforço que vem com toda a garantia do suporte de classe mundial da Riverbed e do investimento contínuo. Saiba mais [neste link](https://www.riverbed.com/office365).

> [!NOTE]
> Sua solução eCDN escolhida está sujeita aos termos de serviço e política de privacidade do provedor de eCDN do parceiro selecionado, que controlará o uso da solução do provedor eCDN. O uso da solução do provedor eCDN não estará sujeito aos termos de licenciamento de volume da Microsoft ou aos Termos de Serviços Online. Se você não concordar com os termos do provedor de terceiros, não habilite a solução eCDN no Microsoft Teams.

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>Configurar eventos de tipo de codificador do Stream para sua solução eCDN

Depois de comprar e configurar sua solução eCDN, você pode habilitá-la para uso com Microsoft Stream, incluindo eventos ao vivo do codificador stream que são criados por meio do Microsoft Teams ou do Yammer.

1. Abra o centro de administração do Teams como um administrador global do Microsoft 365 ou um administrador do Teams e navegue até a página [de configurações de eventos ao vivo](https://admin.teams.microsoft.com/broadcasts/settings) .
1. Alterne o **provedor de distribuição de vídeo** para **Ativado**.
1. Escolha um **provedor eCDN/SDN** na lista suspensa **do provedor de distribuição de vídeo** .
1. Preencha os outros campos conforme dirigido pelo provedor de soluções (nem todos os campos são usados por todos os provedores de solução).
1. Selecione **Salvar**.
1. Para verificar se a configuração está correta, selecione **Verificar configuração**.
    - Pesquise qualquer vídeo em sua organização para validar.
    - Se o provedor eCDN estiver configurado corretamente, você verá uma mensagem **de sucesso** na ferramenta de instalação de verificação.
    - Se você não estiver configurado corretamente, verá uma mensagem **de falha** . Copie a mensagem de evento para compartilhar com seu provedor para solução de problemas.

Depois de configurar o Teams para uma solução eCDN, qualquer vídeo ou evento ao vivo jogado no Teams aproveitará essa solução automaticamente.

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>Configurar eventos de tipo de produção do Teams por meio do Teams e do Yammer para sua solução eCDN

Se você planeja criar eventos ao vivo do Teams por meio do Teams ou do Yammer, precisará [configurar seu provedor eCDN para ser integrado ao Microsoft Teams](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) também.

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>Acessar relatórios de análise de vídeo para sua solução eCDN

Conforme observado acima, algumas soluções eCDN também fornecem relatórios de análise que fornecem informações mais profundas sobre sessões de reprodução, visualizadores e qualidade do serviço. Se o provedor lhe deu um modelo de URL de relatório de análise para configurar quando você configurar o provedor no centro de administração do Teams, os proprietários de vídeos ou eventos poderão facilmente acessar o relatório de análise para um vídeo ou evento específico.

Os proprietários de vídeos verão uma guia Análise diretamente no vídeo. Nesta guia, haverá um link para que os proprietários acessem o relatório de análise para este vídeo específico no sistema do provedor eCDN.

Se você for um administrador do Teams, também poderá elevar seu acesso para ver a guia Análise e acessar o link de relatório de análise do eCDN, mesmo que você não seja proprietário do evento ou vídeo ao vivo.

1. Como administrador do Teams, acesse a página player de vídeo.
1. Selecione **Configurações**.
1. Selecione **Exibir no modo de administração**.
1. Selecione a guia **Análise** .

## <a name="troubleshooting-issues"></a>Solução de problemas

Verifique se sua solução eCDN está configurada corretamente em sua rede e que você configurou corretamente o Teams para habilitar o provedor de acordo com suas instruções e cadeias de caracteres de configuração específicas. Se você ainda estiver tendo problemas, algumas das informações abaixo podem ajudar.

### <a name="verify-setup-tool"></a>Verificar ferramenta de instalação

Se você estiver tendo problemas com sua solução eCDN, sempre poderá voltar e executar a ferramenta **Verificar instalação** . As mensagens de evento do provedor eCDN mostradas para o vídeo de teste podem fornecer a você e ao seu provedor eCDN mais informações sobre o que não está funcionando.

- Vá para **Configurações** >  **Administração Configurações** > **do provedor** >  eCDN **Verificar configuração**

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>Desabilitar o eCDN para uma sessão específica por meio da cadeia de caracteres de consulta de URL

Para determinar se um problema que você está vendo é com a solução eCDN ou com o Teams, você pode desabilitar facilmente a solução eCDN para uma sessão de reprodução específica por meio da cadeia de caracteres de consulta.

- Se sua URL de reprodução já tiver um ponto de interrogação, **?**, nela, adicione **&disableSDN=true**.
- Se sua URL de reprodução não tiver um ponto de interrogação, **?**, nela, adicione **?disableSDN=true**.

### <a name="view-ecdn-info-in-browser-console"></a>Exibir informações do eCDN no console do navegador

Se o provedor de solução eCDN der suporte, ele poderá imprimir informações de depuração durante a inicialização da reprodução por meio da solução. Essas informações extras podem ser úteis para determinar o que está acontecendo de errado. Você pode habilitar mensagens extras de depuração de console por meio da cadeia de caracteres de consulta.

- Se a URL de reprodução já tiver um ponto de interrogação, **?**, nela, adicione **&isSDNDebug=true**.
- Se sua URL de reprodução não tiver um ponto de interrogação, **?**, nela, adicione **?isSDNDebug=true**.

Selecione **F12** no teclado quando o navegador estiver ativo e alterne para a guia **Console** para ver todas as informações impressas durante o carregamento da página com a cadeia de caracteres isSDNDebug=true na URL de reprodução.
