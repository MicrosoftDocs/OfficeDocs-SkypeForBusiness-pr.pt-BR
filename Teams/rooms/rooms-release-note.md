---
title: Notas sobre a versão Salas do Microsoft Teams (Windows)
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Administração pode ler as notas de versão para Salas do Microsoft Teams, que listam melhorias cumulativas no Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cbf840eb8abc60cbdc53325e41b3d9f95e6b4713
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761103"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notas de versão para Salas do Microsoft Teams

Este artigo aborda as melhorias cumulativas no Salas do Microsoft Teams.

Há dois tipos de atualizações para Salas do Teams: atualizações Salas do Teams aplicativo e Teams cliente Web. 

Salas do Teams atualizações de aplicativo ocorrem por meio do Microsoft Store ou por meio [de atualização manual](manual-update.md). Isso atualiza o Plataforma Universal do Windows (UWP) instalado localmente no dispositivo.

Teams atualizações do cliente Web ocorrem por meio dos Teams de entrega de aplicativo Web. Esse é um serviço baseado em nuvem que não requer uma atualização para o aplicativo UWP local instalado no dispositivo.

Para obter mais informações sobre como Teams atualizações, [consulte Teams processo de atualização](../teams-client-update.md)

Salas do Teams é regido pela Política de Ciclo de Vida Moderna. Consulte [Teams processo de atualização](../teams-client-update.md#servicing-agreement) para obter mais informações.

## <a name="version-history"></a>Histórico de versão

|Lançamento |Publicado em <br/> Microsoft Store |
|--- |--- |
|4.12.138.0 |5/26/2022 |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Teams Web-Client versão | Dezembro de 2021 |
|Teams Web-Client versão | Outubro de 2021 |
|4.10.10.0 |10/1/2021 |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8) |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Salas do Microsoft Teams de problemas e introdução ao recurso

### <a name="4121380-5262022"></a>4.12.138.0 (5/26/2022)

Introduzido nesta atualização:
- Correção de bug para vários fluxos de vídeo simultâneos do Jabra Panacast 50 (vídeo de reunião, vídeo de câmera de conteúdo)
- As reuniões entre nuvens agora podem usar o dispositivo de áudio de conferência padrão
- Correções de qualidade e confiabilidade

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

Introduzido nesta atualização:
- Os administradores de TI podem registrar um dispositivo Teams salas para receber recursos de visualização pública por meio da configuração xml. Depois de registrado, o dispositivo começará a receber recursos beta. Todos os recursos que vão para teste beta são anunciados [em Microsoft Teams Versão Prévia Pública – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1,2</sup>  
- O administrador de TI pode definir a resolução de exibição e o dimensionamento do Front of Room remotamente por meio das configurações xml<sup>2</sup>
- O administrador de TI pode desabilitar a supressão de ruído da Microsoft por meio da configuração XML<sup>3</sup> 
- O administrador de TI pode substituir a limpeza da pasta de download no dispositivo por meio da configuração de chave do Registro<sup>4</sup>
- Permitir que os usuários ingressem em uma reunião Teams hospedada em outra nuvem (ou seja, o cliente GCCH pode ingressar em Teams reuniões hospedadas na nuvem comercial e vice-versa) 
- Teams salas agora bloqueiam a inicialização do navegador de borda das URLs no PowerPoint Live como uma medida de segurança adicional para Teams salas com telas de toque 
- A experiência reunir agora foi aprimorada para adicionar instruções para os usuários convidarem usuários para a sala 
- Suporte para Windows 10 versão do recurso 21H2 para Teams salas   
- Novo Cortana de entrada na tela inicial, o botão Compartilhar/apresentar está de volta 

> <sup>1 Instruções</sup> para registrar a versão prévia pública Windows dispositivos podem ser [encontrados aqui](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2 A</sup> resolução de exibição e o dimensionamento de tela front-of-room remotamente por meio de XML podem ser [encontrados aqui](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> No momento, somente a configuração de administrador está sendo liberada. O controle de usuário e a habilitação da supressão de ruído seguirão a versão posterior à 4.12 em maio de 2022. 
>
> <sup>4 Instruções</sup> de limpeza do dispositivo podem ser encontradas [aqui](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 atualização de recursos do 21H2 será atualizada após 7 dias após a instalação do aplicativo ou os administradores podem usar a atualização manual para instalar mais rapidamente. Salas do Microsoft Teams versão 4.12 do aplicativo com essas alterações começará a ser distribuída em abril de 2022 e a distribuição completa em 2 a 3 semanas. As atualizações do aplicativo são entregues Windows armazenamento e o aplicativo é instalado automaticamente. Isso está sendo distribuído Salas do Microsoft Teams somente Windows dados. O que você precisa fazer para se preparar: talvez você queira notificar os usuários sobre essa experiência atualizada e atualizar o treinamento e a documentação conforme apropriado.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introduzido nesta atualização:
- Correção de bug para enquadramento de câmera, o que aprimorará todo o conteúdo no modo de exibição da câmera.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introduzido nesta atualização:
- Layout da linha de frente (versão prévia) para MTR no Windows <sup>1</sup> 
- Administração configuração para definir o layout da linha da frente como padrão  
- Reunir Agora e chamar a atualização do aplicativo Teams somente, Teams os modos de cliente<sup>padrão 1,2</sup>
- Alternar entre várias câmeras de vídeo Teams reuniões<sup>1</sup> 
- Configuração padrão da câmera de vídeo 
- Cortana ícone de push-to-talk no console do MTR 
- Azure AD Premium 1 inclusão de licença no Room Standard e Premium SKUs 
- As políticas de acesso condicional do AAD dão<sup>suporte a 3</sup> 
- Cortana ativação de voz habilitada por padrão no OOBE
- Controles PTZ remotos dão<sup>suporte a 4</sup>

> <sup>1</sup> Esses recursos estão sendo implantados Teams cliente Web e concluirão a distribuição nas próximas duas semanas. Leia mais sobre [Teams atualizações para](../teams-client-update.md) obter detalhes.
> 
> <sup>2</sup> Teams salas no Windows em execução somente no Microsoft Teams ou Skype for Business e Microsoft Teams (padrão) são atualizadas com novas experiências de Reunião e Chamada, no entanto, outros modos não são afetados por essa atualização.
> 
> <sup>3</sup> Consulte detalhes adicionais sobre como configurar políticas [de acesso condicional do AAD](../rooms/rooms-authentication.md#azure-ad-conditional-access) para Salas do Teams.
> 
> <sup>4 Esse recurso</sup> requer que os administradores de TI configurem Teams aplicativo de controles PTZ remotos do cliente de área de trabalho.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Salas do Teams do cliente Web (dezembro de 2021)

Introduzido nesta atualização:
- O layout de vídeo dividido em frente duplo da sala é exibido quando o conteúdo não está sendo compartilhado

### <a name="teams-rooms-web-client-update-october-2021"></a>Salas do Teams do cliente Web (outubro de 2021)

Introduzido nesta atualização:
- Controle unificado de lista de participantes com Teams de área de trabalho com agrupamento de reuniões estruturadas, opções de reunião e controles para apresentadores/participantes, ordem de classificação de mão e capacidade de convidar usuários do chat ou convite de reunião diretamente da lista de participantes 
- O alinhamento de controles de chamada de barra universal com o cliente da área de trabalho em controles de chamada de reunião, botão Layout e informações de status da reunião
- Suporte à galeria dinâmica para telas frontal única e dupla
- Seletor de layout unificado para a opção de layout da frente da sala consolidada
- Destacar ou fixar vários participantes em Teams reuniões
- Suporte a grandes reuniões com controles de apresentador/participantes acessíveis tocando no participante da lista
- Capacidade de bloquear uma reunião para reuniões em que a sala é organizadora, bem como o reconhecimento da reunião que está bloqueada
- Suporte ao consumo do modo de apresentador (weatherman) quando um usuário remoto compartilha conteúdo com a opção de modo de exibição do apresentador
- Suporte a reação em Teams reuniões 

> [!NOTE]
> As atualizações de cliente Web estão disponíveis para todos os Salas do Teams com as versões de aplicativo 4.10 e 4.9. Os administradores poderão se registrar em um Salas do Teams de visualização pública para obter o pico dos recursos do cliente Web em breve.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introduzido nesta atualização:
- A sala remota permite que os usuários controlem a funcionalidade básica da sala usando Teams em seus dispositivos móveis *
- Suporte à câmera de conteúdo de assinatura da Logitech para o botão BLE para compartilhamento na reunião
- As bolhas de chat fornecem notificações no chat da reunião para chamar a atenção para o que está sendo dito usando o chat de reunião *
- O suporte ao modo galeria grande e ao modo Juntos agora está disponível no GCC Alta
- Novas habilidades adicionadas ao Cortana, Adicionar pessoa pelo nome à reunião e Chamar por nome 
- Cortana Push to Talk está habilitado por padrão em todos os dispositivos. Para saber mais, confira [Cortana de voz no Teams](../cortana-in-teams.md).

> [!NOTE]
> Suporte preterido do 19H1. A versão mínima do sistema operacional com suporte na versão 4.10 é 19H2.

> [!NOTE]
> *Esses recursos são distribuídos usando o Teams e funcionarão com todas as versões de aplicativo maiores que a 4.9.

> [!NOTE]
> Para ingressar na reunião agendada do aplicativo móvel do Teams e do MTR-W, localize a conta da sala na lista de participantes no aplicativo móvel do Teams e pressione o menu "Controlar esta sala" e você pode controlar os controles de chamada do aplicativo.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introduzido nesta atualização:
- Microsoft Teams modo somente agora está disponível nas configurações do aplicativo, portanto, você não precisa mais configurar uma Skype for Business conta. Nesse modo, os dispositivos conectados Teams somente ao modo Skype for Business reuniões como um usuário convidado.
- Correção para áudio HDMI causando menor volume de chamadas. O recurso de áudio HDMI é habilitado automaticamente para todos os dispositivos com o build do aplicativo 4.9.12.0.

> [!NOTE]
> Com Skype for Business atingir o fim da vida útil, é recomendável atualizar para Teams modo somente.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introduzido nesta atualização:
- Windows 10 20H2 

> [!NOTE]
> O UC-Engine (data de versão do BIOS que contém "KYSKLi") Salas do Teams tem problemas de compatibilidade e os drivers atualizados serão fornecidos pelos OEMs do sistema em breve. Windows 10 20H2 não será oferecido a esses dispositivos. Para obter mais informações sobre Windows de versão, [consulte Windows 10 de versão](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introduzido nesta atualização:
- Correção de um problema em que as informações de sala Salas do Teams consoles não aparecem para contas de sala ocultas da GAL (lista de endereços global)

> [!NOTE]
> Os clientes GCCH podem baixar o pacote de atualização [de um dispositivo de Salas do Microsoft Teams manualmente](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introduzido nesta atualização:
- Nuvem da Comunidade Governamental suporte a GCCH (alta) para Salas do Teams. Os clientes GCCH com dispositivos Salas do Teams existentes podem baixar a versão 4.8.19.0 de [um dispositivo Salas do Microsoft Teams manualmente](manual-update.md)
- Participe de reuniões do Zoom com melhor qualidade de vídeo (suporte a 720p) e receba a galeria de vídeos dos participantes
- Skype for Business de falha de entrada removida para Teams modo padrão. Essa alteração dá suporte a organizações que removem Skype for Business infraestrutura
- Teams reuniões ingressam na análise de link agora lida com a Proteção Avançada contra Ameaças do Microsoft Defender Cofre Links para permitir a junção de Teams externas diretamente
- Correção para o problema de dimensionamento de conteúdo Skype for Business reuniões quando o computador do sharer tem um DPI personalizado definido em Windows
- Correções de qualidade e confiabilidade

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introduzido nesta atualização:
- Correções de qualidade e confiabilidade

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introduzido nesta atualização:

- Compartilhar áudio HDMI para participantes da reunião Teams reunião
- Cortana de voz (versão prévia)
- Impedir o deslocamento com base em permissões de áudio quando Salas do Teams ingressado como participante. Para obter mais informações, consulte [Gerenciar permissões de áudio do participante em Teams Reuniões](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Destacar o vídeo de alguém do console Teams Room e consumir vídeo em destaque nas telas da sala

> [!NOTE]
> Cortana habilidades de voz estão disponíveis para periféricos de áudio selecionados para locatários localizados no Estados Unidos. Países ou regiões adicionais serão adicionados no futuro. Para obter mais informações, [consulte Cortana de voz no Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introduzido nesta atualização:

- Correção para meia tela branca ao invocar o teclado virtual na Teams reunião

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introduzido nesta atualização:

- Veja mais vídeos com a galeria de vídeos 3x3 na frente das telas da sala  
- Iniciar legendas ocultas ao vivo locais do MTR
- Ingressar em reuniões do Zoom Salas do Teams com ingresso direto de convidado (versão prévia)

> [!NOTE]
> A galeria de vídeos 3x3 e as legendas ocultas ao vivo locais são entregues por meio do Microsoft Teams serviço. Esses recursos estão disponíveis para todos os Salas do Teams com a versão 4.5.37.0 e superior do aplicativo.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introduzido nesta atualização:

- Reuniões coordenadas entre Microsoft Teams e Surface Hub 2S
- Correção para Skype de entrada do Windows 10 For Business quando Windows 10 atualização [KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) ou atualização [Windows 10 KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) estiver instalada

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introduzido nesta atualização:

- Ingressar em reuniões do Cisco WebEx do Salas do Teams com ingresso direto no convidado
- Teams Administração central de habilitação e registro automático
- Windows 10 suporte à versão 1909
- Alternar para o layout da galeria de vídeos mesmo quando o conteúdo estiver presente
- Suporte virtual de levantar mãos para participantes e controles para o apresentador
- Configuração de volume padrão ajustável para conferência e alto-falante padrão
- Pesquisar e chamar usuários federados (locatário) da Teams Room

> [!IMPORTANT]
> A versão 4.5 é a última versão para dar suporte ao Windows 10 versão 1803; as versões futuras não serão oferecidas aos sistemas Windows 10 versão 1803. Para obter mais informações sobre Windows de versão, [consulte Windows 10 de versão](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introduzido nesta atualização:

- Correções de qualidade e confiabilidade
- Correção para o problema "o aplicativo não será iniciado após a atualização para 4.4.41.0"

> [!NOTE]
> Se o dispositivo não atualizar automaticamente para a versão 4.4.63.0, siga as etapas no aplicativo Salas do Microsoft Teams não iniciar após a atualização para [a versão 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) para resolver o problema.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introduzido nesta atualização:

- Correções de confiabilidade para o início do aplicativo Windows 10 Quiosque

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introduzido nesta atualização:

- Suporte de autenticação moderna para Exchange e Skype for Business
- Suporte para chamadas de emergência dinâmicas para Teams (componentes de serviço necessários e liberados usando Teams anéis de cliente)
- Capacidade de desabilitar conteúdo duplicado fora da reunião para salas de exibição dupla usando XML
- Tela inicial do aplicativo
- Avisos de software livre (OSS) nas configurações do dispositivo

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introduzido nesta atualização:

- Atualizações de política para "Windows atualizações para empresas"
- Correção para relatórios de eventos de dispositivo mostrando erro no Azure Monitor

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introduzido nesta atualização:

- Uma correção para um problema de redimensionamento/cintilação de janela que é visto em determinadas configurações
- Processamento de calendário para reuniões de terceiros removido
- Cortana de status removida

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introduzido nesta atualização:

- Resposta automática a chamadas baseadas em proximidade e configuração de administrador para controlar isso
- Atualização Administração Configurações interface do usuário do dispositivo com a adição da configuração do dispositivo na guia Sobre
- Controle de sala de volta para a tela principal
- Sala de Reunião SKU disponível no GCC
- Suporte à câmera de conteúdo Surface Pro sistema baseado em Surface Pro (build mínimo necessário do aplicativo: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introduzido nesta atualização:

- Windows 10 1903. Windows 10 atualização 1903 é oferecida em alguns dias após a atualização do aplicativo
- Correções do teclado virtual não são exibidas de forma confiável

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introduzido nesta atualização:

- Um novo recurso de câmera de conteúdo que permite que os usuários incluam de forma inteligente um quadro de comunicações tradicional em sua Teams reunião
- Melhorias adicionais na interface do usuário do Console para reduzir a confusão e Configurações para uma nova barra lateral que é acessada por meio de Mais no console
- Botão de bandeja de compartilhamento desabilitado se o cabo de conteúdo local não estiver conectado ou se uma câmera de conteúdo não estiver conectada
- Correção de um problema com o teclado virtual em que ele falha ao aparecer pela primeira vez somente após uma reinicialização do sistema MTR
- Correções de qualidade e confiabilidade

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introduzido nesta atualização:

- Skype aplicativo da loja do Sistema de Sala renomear para "Salas do Microsoft Teams"
- Salas do Microsoft Teams interface do usuário do console realinhada para Microsoft Teams
- Atualização de tema: mantenha apenas a imagem de plano de fundo personalizada na frente das telas de exibição da sala, tornando a tela de fundo do console uma cor neutra para garantir que os controles de interface do usuário do console atendam ao contraste de cores — requisitos de acessibilidade
- Barra universal para controles de chamada em reunião para Teams/reuniões para fornecer uma experiência consistente com Microsoft Teams pc/Web/clientes móveis<sup>1</sup>
- Classificação de comentários de qualidade de chamada após Teams chamadas/reuniões<sup>1</sup>
- Receber/renderizar Microsoft Whiteboard na Salas do Microsoft Teams de exibição frontal da sala quando compartilhado do PC/Web/Mobile Teams<sup>cliente 1</sup> <sup>2</sup>
- Remoção do suporte Windows 10 atualizações da versão 1809 devido a problemas de compatibilidade com Salas do Microsoft Teams cliente. Windows 10 suporte à versão 19H1 será adicionado em versões futuras

<sup>1 Microsoft Teams</sup> distribuição de serviço usando Teams anéis. Esse recurso pode estar disponível anterior ou posterior à atualização do cliente 4.0.105.0

<sup>2</sup> Exige que os administradores de TI ativem Microsoft Whiteboard. Além disso, se você tiver uma tela frontal habilitada para toque da sala, deverá calibrar várias exibições de toque usando as configurações do Windows com o logon do administrador do dispositivo para começar a usar o Microsoft Whiteboard para colaboração de uma exibição de sala compartilhada em uma reunião do Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introduzido nesta atualização:

- Corrige um problema com o recurso "fornecer comentários"
- Otimizações em preparação para a próxima atualização Salas do Microsoft Teams dispositivo para Windows 10 versão 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introduzido nesta atualização:

- Correção para o bug de "travamento na inicialização do aplicativo" que afetou os dispositivos no build Windows 10 RS2 herdado.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introduzido nesta atualização:

- Teclado DTMF para Microsoft Teams reuniões P2P e chamadas PSTN. Para tornar Microsoft Teams cliente de chamada padrão, os administradores devem definir IsTeamsDefaultClient como true
- Fixe o vídeo de entrada de um participante remoto em tela inteira na frente da exibição da sala. Usar o comando "Fixar" da lista de participantes no console
- Melhorias nas notificações de lobby com a adição da notificação do Front of Room
- Ícone de transmissão de exibição na frente da sala removido quando Bluetooth sinalizador não está habilitado Salas do Microsoft Teams dispositivo
- Correção do problema de controle de volume em Teams reuniões

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introduzido nesta atualização:

- Exibir conteúdo em ambos os monitores de FoR (Front of Room) em sistemas de sala de tela dupla
- Temas e melhorias na interface do usuário do Front of Room
- Suporte do lado do cliente do TLS 1.2. Para clientes locais, habilitar a comunicação por meio do TLS 1.2 para Salas do Microsoft Teams requer o Skype for Business Server CU9 (Atualização Cumulativa 9) 2015 ou a Atualização Cumulativa 1 do Skype for Business Server 2019 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introduzido nesta atualização:

- Suporte a exibição dupla (front-of-room) para Teams Reuniões

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introduzido nesta atualização:

- Correções de qualidade e confiabilidade

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introduzido nesta atualização:

- Alterações de código necessárias para preparar o Salas do Microsoft Teams para atualização Windows 10 versão 1803
- Correção do problema de formatação com EULAs localizados (especificamente norueguês) que impede o avanço além da janela de instalação OOBE do EULA
- Alterações de código necessárias para fazer com que Salas do Microsoft Teams aplicativo seja executado em sistemas de salas herdados do Lync. Veja mais [aqui](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introduzido nesta atualização:

- O hotfix para o aplicativo Crestron não está sendo iniciado, o que normalmente seria acessível quando o botão do aplicativo em um dispositivo Crestron SR é pressionado. Salas do Microsoft Teams de aplicativo necessário após a instalação da versão 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introduzido nesta atualização:

- Melhorias no recurso "Relatar um problema" Teams modo (equivalente a "Fornecer comentários" no Skype for Business usuário)
- Habilitar a capacidade de fazer fallback do Teams para o Skype for Business para chamadas SIP
- Melhorias de acessibilidade (Narrador, Lupa)
- Reiniciar automaticamente o aplicativo quando necessário depois que as alterações de provisionamento XML forem aplicadas
- Correções diversas

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introduzido nesta atualização:

- Essa atualização permite suporte a reuniões Skype for Business *e Teams* em dispositivos de Sistemas de Sala. Teams é desativado por padrão depois que a atualização é aplicada. Os administradores podem habilitar Teams localmente nas configurações do dispositivo ou por meio de um push xml remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introduzido nesta atualização:

- Correção para resolver o erro observado em alguns sistemas durante a inicialização do aplicativo.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introduzido nesta atualização:

- Alterações que permitem que a Microsoft gerencie atualizações Windows mais flexível.
- Nenhuma alteração na experiência do usuário final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introduzido nesta atualização:

- Correção para resolver problemas de capacidade de resposta do console observados Surface Pro dispositivos baseados em 2017 conectados a duas telas front-of-room e ingestão de vídeo
- Verificação automatizada para garantir que o sistema esteja executando o script de provisionamento mais recente

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introduzido nesta atualização:

- Correção para melhorar o comportamento do OSK (teclado virtual) em sistemas baseados no Windows 10 versão 1709
- Melhorias na preparação para atualizações futuras do sistema operacional

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introduzido nesta atualização:

- Aplicativo atualizado para melhorar a telemetria

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introduzido nesta atualização:

- Corrige um problema em que podem ocorrer problemas intermitentes de ingresso na reunião
- Corrige um problema conhecido por resultar em uma experiência de "travamento" do dispositivo

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introduzido nesta atualização:

- Correções de bug/falha para melhorar a estabilidade
- Suporte para console de tamanho variável
- Descarregamento de processamento de áudio periférico (lista de permissões de mídia adicional)
- Otimizações que permitem que os profissionais de TI criem imagens do tipo "faça você mesmo" com a atualização de janeiro Windows 10 versão 1709 e posteriores.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introduzido nesta atualização:

- Corrige um problema com o recurso "Fornecer Comentários".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introduzido nesta atualização:

- Suporte para hardware [de encaixe do Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Suporte para [a Logitech Brio](https://www.logitech.com/product/brio)
- Resolve um problema em que as exibições (console e front-of-room) falham ao entrar no modo de  sono quando não há nenhuma atividade na sala

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introduzido nesta atualização:

- É executado em um Surface Pro (2017)
- Dá Windows 10 Enterprise Atualização do Criador (idioma inglês, build 1703)
- Suporte para hardware [de encaixe sr da Crestron](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Suporte do OEM para controles de ambiente (Crestron)

A versão de 64 bits do Windows 10 Enterprise Anniversary Edition (em inglês, versão 1607) não tem mais suporte a Salas do Microsoft Teams versão 3.0.12.0 (atualização 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introduzido nesta atualização:

- Resolve problemas observados ao pesquisar usuários federados por meio do campo de pesquisa Participantes. Antes dessa correção, os resultados da pesquisa para usuários federados externos podem não ter resolvido corretamente e, em vez disso, retornaram resultados incorretos.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introduzido nesta atualização:

- Dual-Screen suporte (para paridade do sistema herdado)
- Temas (temas internos e a capacidade de definir o tema personalizado)
- Capacidade de enviar comentários para builds públicos
- Telemetria aprimorada em relação à confiabilidade do ingresso na reunião
- Relatórios Aprimorados do OMS
- Capacidade da ti Administração configurar dispositivos remotamente

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introduzido nesta atualização:

- Seleção de usuário no aplicativo de dispositivos USB de áudio e vídeo da sala de reunião
- Relatório de status do console de sala integrado para clientes que usam o Microsoft Operations Management Suite, agora Azure Monitor

### <a name="release-to-market-1272016"></a>Lançamento no mercado (7/12/2016)

**Recursos:**

 **Projetado para o Skype for Business**

- Reuniões do Skype com apenas um toque
- Reunião do Skype experiência otimizada para salas com vídeo HD de preenchimento de tela e áudio de banda larga HD
- Todos os participantes podem se conectar à Reunião do Skype usando o dispositivo que quiserem, onde quer que estejam
- Convide pessoas a partir de seu diretório, onde você pode ver imediatamente a disponibilidade de cada contato, ou por chamada telefônica
- Compatível com os recursos de Conferência e Chamada PSTN do Skype for Business para substituir o telefone de conferência em sua sala

 **Transforme qualquer sala de reunião**

- Aplicativo dedicado à Reunião do Skype, otimizado para o controlador de tela touch de centro da mesa e para a grande tela frontal da sala
- Reutilizar os investimentos existentes na sua frente de exibição de sala ou projetores
- Funciona para todos os tipos de espaços de reunião, de espaços pequenos a grandes salas de conferência
- Os dispositivos de áudio e vídeo certificados do Skype for Business estão disponíveis para vários tamanhos de sala
- Ingestão com fio interna para o compartilhamento da área de trabalho do projeto para a sala e para o Reunião do Skype

 **Fácil de implantar, simples de gerenciar**

- Dispositivo always-on que ativa automaticamente as telas quando detecta pessoas na sala
- Implantação e atualização simples do aplicativo de Reunião do Skype da UWP (Plataforma Universal do Windows)
- O Windows AppLocker bloqueia o dispositivo para o aplicativo de Reunião do Skype
- Monitorado e gerenciado como um dispositivo Windows 10 Enterprise via Intune e Configuration Manager (MDM)
- Confiabilidade de nível empresarial
- Esforço mínimo para usuários finais devido à semelhança com a interface do usuário do Skype
- É executado no tablet Surface Pro 4

<a name="See"> </a>
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar seu ambiente](rooms-prep.md)

[Suporte para versões Salas do Microsoft Teams Branch Atual](rooms-lifecycle-support.md)

[Problemas conhecidos](known-issues.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
