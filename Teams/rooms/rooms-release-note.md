---
title: Notas de versão para Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: O administrador pode ler as notas de versão Salas do Microsoft Teams, que listam melhorias cumulativas Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3350068646420dcd9a53b1a56c6a144783956e44
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504088"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notas de versão para Salas do Microsoft Teams

Este artigo discute melhorias cumulativas no Salas do Microsoft Teams.

Há dois tipos de atualizações para Salas do Teams: Salas do Teams de aplicativos e Teams Web-client. 

Salas do Teams atualizações de aplicativos ocorrem por meio do Microsoft Store ou por [atualização manual](manual-update.md). Isso atualiza o aplicativo UWP (Plataforma universal de Windows) instalado localmente no dispositivo.

Teams atualizações do cliente Web ocorrem por meio dos serviços Teams de entrega do aplicativo Web. Esse é um serviço baseado em nuvem que não exige uma atualização para o aplicativo UWP local instalado no dispositivo.

Para obter mais informações sobre como Teams atualizações, [consulte Teams processo de atualização](../teams-client-update.md)

Salas do Teams é governada pela Política de Ciclo de Vida Moderna. Consulte [Teams processo de atualização](../teams-client-update.md#servicing-agreement) para obter mais informações.

## <a name="version-history"></a>Histórico de versão

|Versão |Publicado para <br/> Microsoft Store |
|--- |--- |
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

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Salas do Microsoft Teams introdução de recursos e resolução de problemas

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introduzido nesta atualização:
- Correção de bugs para o enquadramento da câmera que aprimorará todo o conteúdo no visualização da câmera.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introduzido nesta atualização:
- Layout da Linha de Frente (Visualização) para MTR no Windows <sup>1</sup> 
- Configuração de administrador para definir o layout da linha de frente como padrão  
- Atender Agora e chamar a atualização do aplicativo Teams somente para Teams de cliente <sup>padrão1,2</sup>
- Alternar entre várias câmeras de vídeo Teams <sup>reuniões1</sup> 
- Configuração padrão da câmera de vídeo 
- Cortana atualização de ícone push-to-talk no console MTR 
- Azure AD Premium 1 inclusão de licença no Room Standard e Premium SKUs 
- AAD políticas de acesso condicional <sup>suportam3</sup> 
- Cortana de voz habilitada por padrão no OOBE
- Suporte a controles PTZ <sup>remotos4</sup>

> <sup>1</sup> Esses recursos estão sendo Teams cliente Web e concluirão a implantação nas próximas duas semanas. Leia mais sobre [Teams para](../teams-client-update.md) obter detalhes.
> 
> <sup>2</sup> Teams salas em Windows em execução somente no Microsoft Teams ou Skype for Business e Microsoft Teams (padrão) são atualizadas com novas experiências de Meet e Call, no entanto, outros modos não são afetados por essa atualização.
> 
> <sup>3</sup> Consulte detalhes de adição sobre a [configuração AAD políticas de acesso](../rooms/rooms-authentication.md#azure-ad-conditional-access) condicional para Salas do Teams.
> 
> <sup>4</sup> Esse recurso exige que os administradores de IT configurem Teams aplicativo de controles PTZ remotos do cliente da área de trabalho.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Salas do Teams do cliente Web (dezembro de 2021)

Introduzido nesta atualização:
- O layout de vídeo dividido em frente dupla é exibido quando o conteúdo não está sendo compartilhado

### <a name="teams-rooms-web-client-update-october-2021"></a>Salas do Teams atualização do cliente Web (outubro de 2021)

Introduzido nesta atualização:
- Controle de lista unificada com Teams de área de trabalho com agrupação de reuniões estruturadas, opções de reunião e controles para apresentadores/participantes, ordem de classificação de mão e capacidade de convidar usuários do Chat ou convite de reunião diretamente da lista de participantes 
- Alinhamento de chamada de barra universal com cliente de área de trabalho em controles de chamada de reunião, botão Layout e informações de status da reunião
- Suporte dinâmico de galeria para exibições de frente única e dupla de sala
- Selador de layout unificado para a opção de layout da frente da sala consolidada
- Destaque ou fixar vários participantes em reuniões Teams reuniões
- Suporte a grandes reuniões com controles de apresentador/participantes acessíveis tocando no participante na lista de participantes
- Capacidade de bloquear uma reunião para reuniões em que a sala é organizadora, bem como a conscientização sobre a reunião que está bloqueada
- Suporte ao consumo do modo apresentador (weatherman) quando um usuário remoto compartilha conteúdo com a opção de modo de exibição do apresentador
- Suporte a reação em Teams reuniões 


> [!NOTE]
> As atualizações do cliente Web estão disponíveis para todos os Salas do Teams com as versões 4.10 e 4.9 do aplicativo. Os administradores poderão se inscrever em um programa de visualização pública Salas do Teams obter o pico dos recursos do cliente Web em breve.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introduzido nesta atualização:
- O controle remoto de sala permite que os usuários controlem a funcionalidade básica da sala usando Teams em seus celulares *
- Logitech scribe content camera support for BLE button for sharing into meeting
- Bolhas de chat fornecem notificações no chat de reunião para chamar a atenção para o que está sendo dito usando o chat de reunião *
- O suporte ao modo galeria grande e ao modo Juntos agora está disponível GCC Alta
- Novas Habilidades adicionadas Cortana, Adicionar pessoa por nome à reunião e Chamada por nome 
- Cortana Push to Talk está habilitado por padrão em todos os dispositivos. Para saber mais, confira [Cortana de voz no Teams](../cortana-in-teams.md).

> [!NOTE]
> Suporte 19H1 preterido. A versão do sistema operacional mínimo com suporte 4.10 é 19H2.

> [!NOTE]
> *Esses recursos são lançados usando o serviço Teams e funcionarão com todas as versões do aplicativo maiores que 4,9.

> [!NOTE]
> Para ingressar na reunião agendada tanto do aplicativo móvel quanto do MTR-W, encontre a conta de sala na lista no aplicativo móvel do Teams e pressione o menu "Controlar essa sala" e você pode controlar os controles de chamada do aplicativo. Teams

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introduzido nesta atualização:
- Microsoft Teams modo somente agora está disponível nas configurações do aplicativo, portanto, você não precisa mais configurar uma Skype for Business de usuário. Nesse modo, os dispositivos conectados Teams somente o modo Skype for Business reuniões como um usuário convidado.
- Correção para áudio HDMI causando menor volume de chamada. O recurso de áudio HDMI é habilitado automaticamente para todos os dispositivos com build de aplicativo 4.9.12.0.

> [!NOTE]
> Com Skype for Business chegar ao fim da vida útil, é recomendável atualizar para Teams modo somente.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introduzido nesta atualização:
- Windows 10 suporte ao 20H2 

> [!NOTE]
> Crestron UC-Engine (data de versão do BIOS que contém "KYSKLi") Salas do Teams problemas de compatibilidade e drivers atualizados serão fornecidos por OEMs do sistema em um futuro próximo. Windows 10 20H2 não será oferecido a esses dispositivos. Para obter mais informações sobre o Windows de versão, [consulte Windows 10 de versão](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introduzido nesta atualização:
- Correção para um problema em que as informações de sala Salas do Teams consoles não aparecem para contas de sala ocultas da GAL (lista de endereços global)

> [!NOTE]
> Os clientes GCCH podem baixar o pacote de atualização [de um dispositivo Salas do Microsoft Teams manualmente](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introduzido nesta atualização:
- Nuvem da Comunidade Governamental suporte a Alta (GCCH) para Salas do Teams. Os clientes GCCH com dispositivos Salas do Teams existentes podem baixar a versão 4.8.19.0 de [um dispositivo Salas do Microsoft Teams manualmente](manual-update.md)
- Participe de reuniões de Zoom com melhor qualidade de vídeo (suporte a 720p) e receba a galeria de vídeo dos participantes
- Skype for Business faixa de falha de login removida para Teams modo padrão. Essa alteração dá suporte a organizações que removem Skype for Business infraestrutura
- Teams reuniões de junção de link agora lidam com a Proteção Avançada contra Ameaças do Microsoft Defender Cofre Links para permitir a junção de Teams externas perfeitamente
- Correção para problemas de dimensionamento de conteúdo compartilhado em reuniões Skype for Business quando o computador do sharer tem um DPI personalizado definido em Windows
- Correções de qualidade e confiabilidade

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introduzido nesta atualização:
- Correções de qualidade e confiabilidade

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introduzido nesta atualização:

- Compartilhar áudio HDMI para participantes de reunião em Teams reunião
- Cortana de voz (Visualização)
- Impedir o deslocamento com base em permissões de áudio quando Teams Room ingressar como participante. Para obter mais informações, consulte [Manage attendee audio permissions in Teams Meetings](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Destaque o vídeo de alguém do console Teams Room e consuma vídeo com destaque em exibições de sala

> [!NOTE]
> Cortana de voz estão disponíveis para selecionar periféricos de áudio para locatários localizados nos Estados Unidos. Países ou regiões adicionais serão adicionados no futuro. Para obter mais informações, [consulte Cortana de voz no Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introduzido nesta atualização:

- Correção para meia-tela branca ao invocar o teclado na tela na Teams reunião

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introduzido nesta atualização:

- Veja mais vídeos com galeria de vídeo 3x3 na frente de exibições de sala  
- Iniciar legendas locais ao vivo fechadas do MTR
- Participar de reuniões do Zoom Salas do Teams com participação direta de convidados (Visualização)

> [!NOTE]
> A galeria de vídeo 3x3 e as legendas fechadas ao vivo locais são entregues por meio do Microsoft Teams serviço. Esses recursos estão disponíveis para todos os Salas do Teams com o aplicativo versão 4.5.37.0 ou superior.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introduzido nesta atualização:

- Reuniões coordenadas entre Microsoft Teams e Surface Hub 2S
- Correção para Skype Windows 10 falha de login para Empresas quando o [KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) ou a atualização Windows 10 [KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) é instalado

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introduzido nesta atualização:

- Participar de reuniões da Cisco WebEx de Salas do Teams com participação direta de convidados
- Teams habilitação e registro automático do Centro de Administração
- Windows 10 suporte a versão 1909
- Alternar para o layout da galeria de vídeo mesmo quando o conteúdo estiver presente
- Suporte de mãos de aumento virtual para o participante e controles para apresentador
- Configuração de volume padrão ajustável para conferência e alto-falante padrão
- Pesquisar e chamar usuários federados (locatário) de Teams Room

> [!IMPORTANT]
> A versão 4.5 é a última versão para dar suporte Windows 10 versão 1803; as versões futuras não serão oferecidas aos sistemas Windows 10 versão 1803. Para obter mais informações sobre o Windows de versão, [consulte Windows 10 de versão](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introduzido nesta atualização:

- Correções de qualidade e confiabilidade
- Correção para "o aplicativo não será lançado após a atualização para o problema 4.4.41.0"

> [!NOTE]
> Se o dispositivo não atualizar automaticamente para a versão 4.4.63.0, siga as etapas no Salas do Microsoft Teams o aplicativo não será ativado após a atualização para [a versão 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) para resolver o problema.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introduzido nesta atualização:

- Correções de confiabilidade para o início do aplicativo Windows 10 Quiosque

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introduzido nesta atualização:

- Suporte à autenticação moderna para Exchange e Skype for Business
- Suporte para chamada de emergência dinâmica para Teams (Componentes de serviço necessários e liberados usando Teams do cliente)
- Capacidade de desabilitar o conteúdo duplicado fora da reunião para salas de exibição dupla usando XML
- Tela inicial do aplicativo
- Avisos de Software de Código Aberto (OSS) nas configurações do dispositivo

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introduzido nesta atualização:

- Atualizações de política para "Windows atualizações para empresas"
- Correção de eventos de dispositivo que mostram erro no Azure Monitor

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introduzido nesta atualização:

- Uma correção para um problema de resizing/cintilação de janela que é visto em determinadas configurações
- Processamento de calendário para reuniões de terceiros removidas
- Cortana configuração de status removida

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introduzido nesta atualização:

- Atender automaticamente chamadas baseadas em proximidade e configuração de administrador para controlar isso
- Atualização da interface do usuário Configurações administrador de dispositivos com adição da configuração do dispositivo na guia Sobre
- Controle de sala de volta para a tela principal
- Sala de Reunião SKU disponível no GCC
- Suporte à câmera de conteúdo Surface Pro sistema baseado em Surface Pro (com build mínimo necessário do aplicativo: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introduzido nesta atualização:

- Windows 10 suporte a 1903. Windows 10 atualização 1903 é oferecida em alguns dias após a atualização do aplicativo
- Correções para teclado na tela não aparecer de forma confiável

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introduzido nesta atualização:

- Um novo recurso de câmera de conteúdo que permite que os usuários incluam de forma inteligente um quadro de Teams tradicional
- Melhorias adicionais na interface do usuário do Console para reduzir a desordem e Configurações para uma nova barra lateral acessada por meio de Mais no console
- Botão de bandeja de compartilhamento desabilitado se o cabo de conteúdo local não estiver conectado ou uma câmera de conteúdo não estiver conectada
- Corrigido um problema com o teclado touch em que ele falhou ao aparecer pela primeira vez somente após a reinicialização de um sistema MTR
- Correções de qualidade e confiabilidade

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introduzido nesta atualização:

- Skype aplicativo da Loja do Sistema de Sala renomear para "Salas do Microsoft Teams"
- Salas do Microsoft Teams interface do usuário do console realinhada para Microsoft Teams
- Atualização de tema: mantenha apenas a imagem de plano de fundo personalizada na frente das exibições de sala, enquanto faz do plano de fundo do console uma cor neutra para garantir que os controles da interface do usuário do console atendem ao contraste de cores— requisitos de acessibilidade
- Barra universal para controles de chamada em reunião para Teams chamadas/reuniões para fornecer uma experiência consistente com Microsoft Teams clientes pc/Web/<sup>Mobile1</sup>
- Classificação de feedback de qualidade de chamada após Teams chamadas/<sup>reuniões1</sup>
- Recebimento/renderização Microsoft Whiteboard na tela Salas do Microsoft Teams da sala de exibição quando compartilhado do computador/ Web/ mobile Teams <sup>cliente1</sup> <sup>2</sup>
- Foi removido o suporte Windows 10 atualizações da versão 1809 devido a problemas de compatibilidade com Salas do Microsoft Teams cliente. Windows 10 suporte à versão 19H1 será adicionado em versões futuras

<sup>1</sup> Microsoft Teams distribuição de serviço usando Teams anéis. Esse recurso pode estar disponível anterior ou posterior à atualização do cliente 4.0.105.0

<sup>2</sup> Exige que os administradores de IT a Microsoft Whiteboard. Além disso, se você tiver uma tela frontal habilitada para toque da sala, deverá calibrar várias exibições de toque usando configurações de Windows com o logon do administrador do dispositivo para começar a usar o Microsoft Whiteboard para colaboração a partir de uma exibição de sala compartilhada em uma reunião de Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introduzido nesta atualização:

- Corrige um problema com o recurso "dar feedback"
- Otimizações em preparação para a próxima atualização Salas do Microsoft Teams dispositivo para Windows 10 versão 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introduzido nesta atualização:

- Correção para o bug "trava no início do aplicativo" que afetava dispositivos em uma com Windows 10 RS2 herdada.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introduzido nesta atualização:

- Teclado DTMF para reuniões Microsoft Teams P2P e chamadas PSTN. Para tornar Microsoft Teams cliente de chamada padrão, os administradores devem definir IsTeamsDefaultClient como true
- Fixar o vídeo de entrada de um participante remoto na tela inteira na tela frontal da sala. Usar o comando "Pin" da lista de participantes no console
- Melhorias nas notificações de lobby com adição de notificação de Front of Room
- Ícone de transmissão de exibição na frente da sala removido quando Bluetooth sinalizador não está habilitado no Salas do Microsoft Teams dispositivo
- Correção do problema de controle de volume em Teams reuniões

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introduzido nesta atualização:

- Exibir conteúdo em ambos os front of room (FoR) é exibido em sistemas de sala de tela dupla
- Temas e melhorias na interface do usuário do Front of Room
- Suporte do lado do cliente TLS 1.2. Para clientes locais, a habilitação da comunicação por meio do TLS 1.2 para o Salas do Microsoft Teams requer a atualização cumulativa 9 (CU9) do Skype for Business Server 2015 ou a Atualização Cumulativa 1 do Skype for Business Server 2019 2019 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introduzido nesta atualização:

- Suporte para exibição dupla (Front of Room) para Teams Reuniões

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introduzido nesta atualização:

- Correções de qualidade e confiabilidade

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introduzido nesta atualização:

- Alterações de código necessárias para preparar o aplicativo Salas do Microsoft Teams para a atualização Windows 10 versão 1803
- Correção de problemas de formatação com EULAs localizadas (especificamente norueguês) que impede o avanço além da janela de configuração OOBE da EULA
- Alterações de código necessárias para fazer com que Salas do Microsoft Teams aplicativo seja executado em sistemas de sala herdados do Lync. Veja mais [aqui](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introduzido nesta atualização:

- Hotfix para o aplicativo Crestron não sendo lançado, o que normalmente seria acessível quando o botão do aplicativo em um dispositivo SR Crestron é pressionado. Salas do Microsoft Teams a reinicialização do aplicativo necessária após a instalação de 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introduzido nesta atualização:

- Melhorias do recurso "Relatar um Problema" no modo Teams (equivalente a "Dar feedback" no Skype for Business modo)
- Habilitar a capacidade de voltar do Teams para o Skype for Business para chamadas SIP
- Melhorias de acessibilidade (Narrador, Lupa)
- Reiniciar automaticamente o aplicativo quando necessário após as alterações de provisionamento XML foram aplicadas
- Correções diversas

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introduzido nesta atualização:

- Essa atualização permite suporte a reuniões Skype for Business *e Teams* em dispositivos de Sistemas de Sala. Teams está desligado por padrão depois que a atualização é aplicada. Os administradores podem habilitar Teams localmente nas configurações do dispositivo ou por meio de um push xml remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introduzido nesta atualização:

- Correção para corrigir o erro de endereço observado em alguns sistemas durante a iniciação do aplicativo.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introduzido nesta atualização:

- Alterações que permitem que a Microsoft gerencie mais Windows Atualizações.
- Nenhuma alteração na experiência do usuário final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introduzido nesta atualização:

- Correção para resolver problemas de capacidade de resposta do console observados Surface Pro dispositivos baseados em 2017 conectados a duas exibições front-of-room e ingestão de vídeo
- Verificação automatizada para garantir que o sistema está executando o script de provisionamento mais recente

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introduzido nesta atualização:

- Correção para melhorar o comportamento do OSK (teclado na tela) nos sistemas baseados na Janela 10 Versão 1709
- Melhorias para se preparar para atualizações futuras do sistema operacional

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introduzido nesta atualização:

- Aplicativo atualizado para melhorar a telemetria

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introduzido nesta atualização:

- Corrige um problema em que podem ocorrer problemas de junção de reuniões intermitentes
- Corrige um problema conhecido por resultar em uma experiência de "trava" do dispositivo

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introduzido nesta atualização:

- Correções de bugs/falhas para melhorar a estabilidade
- Suporte para console de tamanho variável
- Descarregamento de processamento de áudio periférico (lista de permitir mídia adicional)
- Otimizações que permitem que os profissionais de TI criem imagens do -it-yourself com Windows 10 Versão 1709 atualização de janeiro e posteriores.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introduzido nesta atualização:

- Corrige um problema com o recurso "Dar feedback".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introduzido nesta atualização:

- Suporte para hardware [de encaixe da série Polycom MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Suporte para [a Logitech Brio](https://www.logitech.com/product/brio)
- Resolve um problema em que as exibições (console e front-of-room) não entram no modo de  sono quando não há atividade na sala

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introduzido nesta atualização:

- Executa em um tablet Surface Pro (2017)
- Oferece suporte Windows 10 Enterprise Atualização do Criador (idioma inglês, build 1703)
- Suporte para hardware [de encaixe SR crestron](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Suporte do OEM para controles de ambiente (Crestron)

A versão de 64 bits do Windows 10 Enterprise Anniversary edition (idioma inglês, versão 1607) não é mais suportada Salas do Microsoft Teams versão 3.0.12.0 (atualização 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introduzido nesta atualização:

- Resolve problemas observados ao pesquisar usuários federados por meio do campo de pesquisa Participantes. Antes dessa correção, os resultados da pesquisa para usuários federados externos podem não ter resolvido corretamente e, em vez disso, retornaram resultados incorretos.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introduzido nesta atualização:

- Dual-Screen suporte (para paridade do sistema herdou)
- Temas (temas integrados e a capacidade de definir tema personalizado)
- Capacidade de dar feedback para builds públicas
- Telemetria aprimorada em torno da confiabilidade de junção de reunião
- Relatórios OMS aprimorados
- Capacidade para o administrador de IT configurar dispositivos remotamente

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introduzido nesta atualização:

- Seleção de usuários no aplicativo de dispositivos USB de áudio e vídeo de sala de reunião
- Relatório de status do console de sala integrado para clientes que usam o Microsoft Operations Management Suite, agora o Azure Monitor

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
- Reutilizar investimentos existentes na tela frontal da sala ou projetores
- Funciona para todos os tipos de espaços de reunião, de espaços pequenos a grandes salas de conferência
- Os dispositivos de áudio e vídeo certificados do Skype for Business estão disponíveis para vários tamanhos de sala
- Ingestão com fio integrado para projetar o compartilhamento de área de trabalho para a sala e para o Reunião do Skype

 **Fácil de implantar, simples de gerenciar**

- Dispositivo always-on que acorda automaticamente as exibições quando detecta pessoas na sala
- Implantação e atualização simples do aplicativo de Reunião do Skype da UWP (Plataforma Universal do Windows)
- O Windows AppLocker bloqueia o dispositivo para o aplicativo de Reunião do Skype
- Monitorado e gerenciado como um Windows 10 Enterprise por meio do Intune e do Configuration Manager (MDM)
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
