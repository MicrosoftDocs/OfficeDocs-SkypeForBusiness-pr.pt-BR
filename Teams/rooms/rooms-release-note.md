---
title: Notas de versão para Salas do Microsoft Teams (Windows)
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
- Teams_ITAdmin_Rooms
description: Administração pode ler as notas de versão para Salas do Microsoft Teams, que listam melhorias cumulativas no Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c6416115d65f223b3785be050520548c2e69ba4
ms.sourcegitcommit: 23224d983ae027c4923e52ed8e31953ae0f84807
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69422810"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notas de versão para Salas do Microsoft Teams

Este artigo discute melhorias cumulativas no Salas do Microsoft Teams.

Há dois tipos de atualizações para Salas do Teams: Salas do Teams atualizações de aplicativo e cliente Web do Teams.

Salas do Teams atualizações de aplicativo acontecem por meio da Microsoft Store ou por meio de [atualização manual](manual-update.md). Atualizações são aplicados ao aplicativo UWP (Plataforma Universal do Windows) instalado localmente no dispositivo.

As atualizações do cliente Web do Teams acontecem por meio dos serviços de entrega de aplicativos Web do Teams. O cliente Web do Teams é um serviço baseado em nuvem que não requer uma atualização para o aplicativo UWP local instalado no dispositivo.

Para obter mais informações sobre como o Teams atualiza, confira [Processo de atualização do Teams](../teams-client-update.md)

Salas do Teams é regido pela Política de Ciclo de Vida Moderna. Para obter mais informações, confira [Processo de atualização do Teams](../teams-client-update.md#servicing-agreement).

## <a name="version-history"></a>Histórico de versões

|Lançamento |Publicado para <br/> Microsoft Store |
|--- |--- |
|4.15.54.0 | 12/15/2022 |
|4.14.24.0 |9/2/2022 |
|4.13.132.0 |8/2/2022 |
|4.12.139.0 |7/14/2022 |
|4.12.138.0 |5/26/2022 |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Versão do cliente Web do Teams | dezembro de 2021 |
|Versão do cliente Web do Teams | outubro de 2021 |
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

### <a name="415540-12152022"></a>4.15.54.0 (12/15/2022)

Introduzido nesta atualização:

- Aprimoramento de notificação em reunião
- Chat de reunião na Galeria, galeria grande e modo Juntos <sup>1</sup>
- Iniciar quadro de informações em reuniões do Teams
- Controle de lista de vídeos da sala de ajuste ao quadro
- Suporte à reunião de estouro
- Ingressar na reunião do Zoom por ID (ingresso de convidado direto)
- Correções de qualidade para reuniões de terceiros (ingresso de convidado direto)
- Correção de informações de licença em configurações que não mostram nenhuma licença quando o Teams não está conectado
- Um novo papel de parede padrão (Vivid Flag) e outros quatro novos papéis de parede

<sup>1</sup> A configuração de administrador para ocultar o chat de reunião de todos os layouts de reunião por meio do XML pode ser encontrada em [Gerenciar uma Salas do Microsoft Teams configurações de console remotamente com um arquivo de configuração XML](xml-config-file.md).

### <a name="414240-922022"></a>4.14.24.0 (9/2/2022)

Introduzido nesta atualização:

- Atualização da experiência de layout da primeira linha
- Fixar e ocultar vídeo da sala
- Configuração do administrador para desativar a galeria dividida em exibição dupla Salas do Teams <sup>1</sup>
- O Salas do Teams de exibição dupla agora pode exibir até 18 fluxos de vídeo participantes
- Suporte para licenças de sala Salas Microsoft Teams Pro e Microsoft Teams Room Basic

<sup>1</sup> A configuração do administrador para desativar a galeria dividida por meio do XML pode ser encontrada em [Gerenciar uma Salas do Microsoft Teams configurações de console remotamente com um arquivo de configuração XML](../rooms/xml-config-file.md).

### <a name="4131320-822022"></a>4.13.132.0 (8/2/2022)

Introduzido nesta atualização:

- Ingressar na reunião do Teams usando a ID da reunião
- Criptografia de ponta a ponta para chamadas de um para um do Teams<sup>1</sup> 
- Supressão de ruído nas reuniões<sup>do Teams 2</sup>
- Atualização da experiência da bandeja de compartilhamento
- Silenciar e desmutar o status no vídeo do quarto
- Administração configuração para o padrão de layout somente de conteúdo  
- A autenticação moderna está ativada por padrão

 <sup>1</sup> Antes de ativar a criptografia de ponta a ponta para chamadas de um dispositivo Salas do Teams, você precisa configurar a política para a conta de usuário do dispositivo. Você pode atualizar a política do usuário do centro de administração do Teams ou usando o Teams PowerShell. Para obter mais informações, consulte [Configurar a política para a conta de usuário do Teams Room.](../teams-end-to-end-encryption.md)

 <sup>2</sup> Salas do Teams adicionado suporte para supressão de ruído na versão 4.12 com substituição de administrador.

> [!IMPORTANT]
> Com essa atualização, novos dispositivos Salas do Teams agora padrão para usar a autenticação moderna ao se conectar ao Microsoft Teams e Exchange Online.
>
> Recomendamos que você teste seus dispositivos Salas do Teams antes do final de agosto ativando a autenticação moderna para suas contas de quarto.
>
> Essa alteração ajuda a se preparar para a próxima atualização no Exchange Online desativar a autenticação básica a partir de 1º de outubro de 2022. Para obter mais informações, consulte [Preterição de autenticação básica no Exchange Online – Atualização de maio de 2022 ](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-may-2022/ba-p/3301866).  

### <a name="4121390-7142022"></a>4.12.139.0 (7/14/2022)

Introduzido nesta atualização:

- Altera o número da versão para permitir que os sistemas afetados pelo Windows [KB5013942](https://support.microsoft.com/topic/may-10-2022-kb5013942-os-builds-19042-1706-19043-1706-and-19044-1706-60b51119-85be-4a34-9e21-8954f6749504) registrem novamente o aplicativo para que ele possa ser iniciado. Não há alterações funcionais nesta versão do aplicativo de 4.1.2.138.0.

> [!NOTE]
> Para obter mais informações, consulte "Salas do Teams aplicativo falha ao iniciar após a atualização" em [Problemas conhecidos em Salas do Teams e dispositivos](/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues).

### <a name="4121380-5262022"></a>4.12.138.0 (5/26/2022)

Introduzido nesta atualização:
- Correção de bug para vários fluxos de vídeo simultâneos do Jabra Panacast 50 (vídeo de reunião, vídeo da câmera de conteúdo)
- As reuniões entre nuvem agora podem usar o dispositivo de áudio de conferência padrão
- Correções de qualidade e confiabilidade

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

Introduzido nesta atualização:
- Os administradores de TI podem registrar um dispositivo de salas do Teams para receber recursos de visualização pública por meio da configuração XML. Depois de registrado, o dispositivo começará a receber recursos beta. Todos os recursos que vão para testes beta são anunciados em [Microsoft Versão Prévia Pública do Teams - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1,2</sup>  
- O administrador de TI pode definir a resolução de exibição Front of Room e dimensionar remotamente por meio das configurações XML<sup>2</sup>
- O administrador de TI pode desabilitar Microsoft supressão de ruído por meio da configuração<sup>XML 3</sup> 
- O administrador de TI pode substituir a limpeza da pasta de download no dispositivo por meio da configuração<sup>da</sup> chave do registro 4
- Permitindo que os usuários participem da reunião do Teams hospedada em outra nuvem (ou seja, o cliente do GCCH pode ingressar em reuniões do Teams hospedadas na nuvem comercial e vice-versa) 
- As salas do Teams agora bloqueiam o lançamento do navegador de borda de URLs no PowerPoint Live como uma medida de segurança adicional para salas do Teams com exibições de toque 
- A experiência do Meet now é aprimorada para adicionar instruções para que os usuários convidem os usuários para a sala 
- Suporte para Windows 10 versão do recurso 21H2 para salas do Teams   
- Novo ponto de entrada da Cortana na tela inicial, o botão Compartilhar/presente está de volta 

> <sup>1</sup> Instruções para registrar dispositivos MTR Windows de visualização pública podem ser encontradas [aqui](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> A resolução de exibição da frente da sala e o dimensionamento remotamente por meio do XML podem ser encontrados [aqui](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> No momento, somente a configuração de administrador está sendo liberada. O controle do usuário e a habilitação da supressão de ruído seguirão a versão pós 4.12 em maio de 2022. 
>
> <sup>4</sup> Instruções de limpeza de dispositivo podem ser encontradas [aqui](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 atualização do recurso 21H2 será atualizada após 7 dias de instalação do aplicativo ou os administradores podem usar a atualização manual para instalar mais rapidamente. Salas do Microsoft Teams aplicativo versão 4.12 com essas alterações, começará a ser implementado em abril de 2022 e concluirá a distribuição em 2 a 3 semanas. As atualizações do aplicativo são entregues por meio do Windows Store e o aplicativo é instalado automaticamente. Isso está sendo implantado apenas em Salas do Microsoft Teams no Windows. O que você precisa fazer para se preparar: talvez você queira notificar seus usuários sobre essa experiência atualizada e atualizar seu treinamento e documentação conforme apropriado.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introduzido nesta atualização:
- Correção de bug para enquadramento de câmera que aprimorará todo o conteúdo no modo de exibição da câmera.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introduzido nesta atualização:
- Layout da primeira linha (versão prévia) para MTR no Windows<sup>1</sup> 
- Administração configuração para definir o layout da primeira linha como padrão  
- Conheça agora e chame a atualização do aplicativo somente para o Teams, modos de cliente padrão<sup>do Teams 1,2</sup>
- Alternar entre várias câmeras de vídeo nas reuniões<sup>do Teams 1</sup> 
- Configuração padrão da câmera de vídeo 
- Atualização de ícone push-to-talk da Cortana no console do MTR 
- Azure AD inclusão de licença Premium 1 em SKUs Padrão de Sala e Premium 
- As políticas de acesso condicional do AAD dão suporte<sup>a 3</sup> 
- Ativação de voz da Cortana habilitada por padrão no OOBE
- Controles PTZ remotos dão suporte<sup>a 4</sup>

> <sup>1</sup> Esses recursos estão sendo implantados usando o cliente Web do Teams e concluirão a distribuição nas próximas semanas. Leia mais sobre [as atualizações do Teams](../teams-client-update.md) para obter detalhes.
> 
> <sup>Duas</sup> salas do Teams no Windows em execução no Microsoft Teams somente ou Skype for Business e Microsoft Teams (padrão) são atualizadas com novas experiências de Atender e Chamar, no entanto, outros modos não são afetados por essa atualização.
> 
> <sup>3</sup> Confira detalhes de adição sobre como configurar políticas de [acesso condicional do AAD](../rooms/rooms-authentication.md#azure-ad-conditional-access) para Salas do Teams.
> 
> <sup>4</sup> Esse recurso exige que os administradores de TI configurem o aplicativo de controles PTZ remoto do cliente da área de trabalho do Teams.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Salas do Teams atualização do cliente Web (dezembro de 2021)

Introduzido nesta atualização:
- Dividir o layout de vídeo em exibições duplas da Frente da Sala quando o conteúdo não está sendo compartilhado

### <a name="teams-rooms-web-client-update-october-2021"></a>Salas do Teams atualização do cliente Web (outubro de 2021)

Introduzido nesta atualização:
- Controle de lista unificada com o cliente da área de trabalho do Teams com agrupamento de reuniões estruturadas, opções de reunião e controles para apresentadores/participantes, ordem de classificação manual e capacidade de convidar usuários do Chat ou convite de reunião diretamente da lista 
- Alinhamento de controles de chamada de barra universal com o cliente da área de trabalho em controles de chamada de reunião, botão Layout e informações de status da reunião
- Suporte de galeria dinâmica para exibições de frente única e dupla da sala
- Seletor de layout unificado para a opção de layout da frente da sala consolidada
- Destaque ou Fixar vários participantes em reuniões do Teams
- Grandes reuniões dão suporte a controles de apresentador/participantes acessíveis tocando no participante da lista
- Capacidade de bloquear uma reunião para reuniões onde a sala é organizadora, bem como a conscientização da reunião que está bloqueada
- Suporte ao consumo do modo de apresentador (meteorologista) quando um usuário remoto compartilha conteúdo com a opção de exibição do apresentador
- Suporte à reação em reuniões do Teams 

> [!NOTE]
> As atualizações do cliente Web estão disponíveis para todos os Salas do Teams com as versões do aplicativo 4.10 e 4.9. Os administradores poderão se inscrever em Salas do Teams programa de visualização pública para obter o pico sorrateiro dos recursos do cliente Web em breve.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introduzido nesta atualização:
- O controle remoto da sala permite que os usuários controlem a funcionalidade básica da sala usando o Teams em seu celular *
- Suporte à câmera de conteúdo do escriba logitech para botão BLE para compartilhamento em reunião
- As bolhas de chat fornecem notificações para no chat da reunião para chamar a atenção para o que está sendo dito usando o chat de reunião *
- A galeria grande e o suporte ao modo Juntos já estão disponíveis no GCC High
- Novas habilidades adicionadas à Cortana, Adicionar pessoa por nome à reunião e Chamar pelo nome 
- O Push to Talk da Cortana está habilitado por padrão em todos os dispositivos. Para saber mais, confira [Assistência de voz da Cortana no Teams](../cortana-in-teams.md).

> [!NOTE]
> Suporte preterido de 19H1. A versão do sistema operacional min com suporte para 4.10 é 19H2.

> [!NOTE]
> *Esses recursos são implantados usando o serviço do Teams e funcionarão com todas as versões do aplicativo maiores que 4.9.

> [!NOTE]
> Para participar da reunião agendada tanto do aplicativo Teams Mobile quanto do MTR-W, encontre a conta da sala na lista no aplicativo Teams Mobile e pressione "Controlar esta sala" e você pode controlar controles de chamada do aplicativo.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introduzido nesta atualização:
- Microsoft modo somente do Teams agora está disponível nas configurações do aplicativo, portanto, você não precisa mais configurar uma conta Skype for Business. Nesse modo, os dispositivos conectados ao modo somente do Teams entram Skype for Business reuniões como usuário convidado.
- Correção para áudio HDMI causando menor volume de chamada. O recurso de áudio HDMI está habilitado automaticamente para todos os dispositivos com o build de aplicativo 4.9.12.0.

> [!NOTE]
> Com Skype for Business atingindo o fim da vida útil, é recomendável atualizar para o modo somente do Teams.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introduzido nesta atualização:
- Windows 10 suporte a 20H2 

> [!NOTE]
> Crestron UC-Engine (data da versão do BIOS que contém "KYSKLi") Salas do Teams tiver problemas de compatibilidade e drivers atualizados serão fornecidos por OEMs do sistema em um futuro próximo. Windows 10 20H2 não serão oferecidos a esses dispositivos. Para obter mais informações sobre o suporte à versão do Windows, consulte [Windows 10 suporte à versão](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introduzido nesta atualização:
- Correção para um problema em que as informações de sala em consoles Salas do Teams não aparecem para contas de quarto ocultas da GAL (lista de endereços global)

> [!NOTE]
> Os clientes do GCCH podem baixar o pacote de atualização de [atualizar manualmente um dispositivo Salas do Microsoft Teams](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introduzido nesta atualização:
- Suporte do GCCH (Government Community Cloud High) para Salas do Teams. Os clientes do GCCH com dispositivos Salas do Teams existentes podem baixar a versão 4.8.19.0 da [atualização manual de um dispositivo Salas do Microsoft Teams](manual-update.md)
- Participe de reuniões do Zoom com melhor qualidade de vídeo (suporte a 720p) e receba a galeria de vídeos dos participantes
- Skype for Business faixa de falha de entrada removida para o modo padrão do Teams. Essa alteração dá suporte a organizações que removem Skype for Business infraestrutura
- As reuniões do Teams juntam a análise de link agora lida com Microsoft Defender Links Avançados de Proteção contra Ameaças para permitir a junção do Teams externos perfeitamente
- Correção do problema de dimensionamento de conteúdo compartilhado em reuniões de Skype for Business quando o computador do sharer tem uma DPI personalizada definida no Windows
- Correções de qualidade e confiabilidade

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introduzido nesta atualização:
- Correções de qualidade e confiabilidade

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introduzido nesta atualização:

- Compartilhar áudio HDMI para os participantes da reunião do Teams
- Habilidades de voz da Cortana (versão prévia)
- Impedir o deslocamento com base em permissões de áudio quando Salas do Teams ingressar como participante. Para obter mais informações, consulte [Gerenciar permissões de áudio do participante em Reuniões do Teams](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Destacar o vídeo de alguém do console do Teams Room e consumir vídeos com destaque em exibições de sala

> [!NOTE]
> As habilidades de voz da Cortana estão disponíveis para selecionar periféricos de áudio para locatários localizados no Estados Unidos. Outros países ou regiões serão adicionados no futuro. Para obter mais informações, confira [Assistência de voz da Cortana no Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introduzido nesta atualização:

- Correção para meia tela branca ao invocar teclado na tela na reunião do Teams

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introduzido nesta atualização:

- Confira mais vídeos com a galeria de vídeos 3x3 na frente das exibições de sala  
- Iniciar legendas fechadas ao vivo local do MTR
- Ingressar em reuniões do Zoom de Salas do Teams com ingresso direto de convidado (Versão prévia)

> [!NOTE]
> A galeria de vídeo 3x3 e as legendas fechadas ao vivo locais são entregues por meio do serviço Microsoft Teams. Esses recursos estão disponíveis para todos os dispositivos Salas do Teams com a versão do aplicativo 4.5.37.0 e superior.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introduzido nesta atualização:

- Reuniões coordenadas entre Microsoft Teams e Surface Hub 2S
- Correção para falha de entrada do Skype For Business quando [Windows 10 atualização KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) ou [Windows 10 atualização KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) é instalada

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introduzido nesta atualização:

- Ingressar em reuniões do Cisco Webex de Salas do Teams com ingresso direto de convidado
- Habilitação e registro automático do Teams Administração Center
- Windows 10 suporte à versão de 1909
- Alternar para o layout da galeria de vídeo mesmo quando o conteúdo estiver presente
- Suporte de mãos levantadas virtuais para participante e controles para apresentador
- Configuração de volume padrão ajustável para conferência e alto-falante padrão
- Pesquisar e chamar usuários federados (locatário) da Sala do Teams

> [!IMPORTANT]
> A versão 4.5 é a última versão a dar suporte a Windows 10 versão 1803; versões futuras não serão oferecidas aos sistemas na versão 1803 Windows 10. Para obter mais informações sobre o suporte à versão do Windows, consulte [Windows 10 suporte à versão](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introduzido nesta atualização:

- Correções de qualidade e confiabilidade
- Correção para o problema "o aplicativo não será iniciado após a atualização para 4.4.41.0"

> [!NOTE]
> Se o dispositivo não for atualizado automaticamente para a versão 4.4.63.0, siga as etapas em [Salas do Microsoft Teams aplicativo não será iniciado após a atualização para a versão 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) para resolver o problema.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introduzido nesta atualização:

- Correções de confiabilidade para início do aplicativo no Quiosque Windows 10

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introduzido nesta atualização:

- Suporte de autenticação moderna para Exchange e Skype for Business
- Suporte para chamada de emergência dinâmica para o Teams (componentes de serviço necessários e liberados usando anéis de cliente do Teams)
- Capacidade de desabilitar conteúdo duplicado fora da reunião para salas de exibição duplas usando XML
- Tela de respingo de aplicativo
- Avisos do OSS (Software de Código Aberto) nas configurações do dispositivo

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introduzido nesta atualização:

- Atualizações de política para "Windows Atualizações for Business"
- Correção para relatórios de eventos de dispositivo mostrando erro no Azure Monitor

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introduzido nesta atualização:

- Uma correção para um problema de redimensionamento/cintilação da janela que é visto em determinadas configurações
- Processamento de calendário para reuniões de terceiros removido
- Configuração de status da Cortana removida

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introduzido nesta atualização:

- Atender automaticamente chamadas baseadas em proximidade e configuração de administrador para controlar isso
- Atualização da interface do usuário de configurações do dispositivo Administração com adição da configuração do dispositivo na guia Sobre
- Controle de sala de volta à tela principal
- SKU da Sala de Reunião disponível no GCC
- Suporte à câmera de conteúdo para o sistema baseado em Surface Pro (build de aplicativo necessário mínimo: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introduzido nesta atualização:

- Windows 10 suporte a 1903. Windows 10 atualização de 1903 é oferecida em alguns dias após a atualização do aplicativo
- Correções para teclado na tela não aparecendo de forma confiável

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introduzido nesta atualização:

- Um novo recurso de câmera de conteúdo que permite que os usuários incluam inteligentemente um quadro de dados tradicional em sua reunião do Teams
- Melhorias adicionais na interface do usuário do console para reduzir a desordem e mover configurações para uma nova barra lateral que é acessada por meio de Mais no console
- Botão de bandeja de compartilhamento desabilitado se o cabo de conteúdo local não estiver conectado ou uma câmera de conteúdo não estiver conectada
- Corrigido um problema com o teclado sensível ao toque em que ele não apareceu pela primeira vez somente após uma reinicialização do sistema MTR
- Correções de qualidade e confiabilidade

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introduzido nesta atualização:

- O aplicativo da loja do Skype Room System renomeia para "Salas do Microsoft Teams"
- Salas do Microsoft Teams interface do usuário do console realinhada para Microsoft Teams
- Atualização do tema: mantenha apenas a imagem de fundo personalizada na frente das exibições de sala, tornando o plano de fundo do console uma cor neutra para garantir que os controles de interface do usuário do console atendam ao contraste de cores— requisitos de acessibilidade
- Barra universal para controles de chamada em reunião para chamadas/reuniões do Teams para fornecer uma experiência consistente com Microsoft clientes do Teams PC/Web/Mobile<sup>1</sup>
- Classificação de comentários de qualidade de chamada após chamadas do Teams/reuniões<sup>1</sup>
- Receber/renderizar Microsoft Whiteboard em Salas do Microsoft Teams frente da exibição da sala quando compartilhado do pc/Web/ cliente do Mobile Teams<sup>1</sup> <sup>2</sup>
- Removeu o suporte para atualizações Windows 10 versão 1809 devido a problemas de compatibilidade com Salas do Microsoft Teams cliente. Windows 10 suporte à versão 19H1 será adicionado em versões futuras

<sup>1</sup> Microsoft distribuição de serviço do Teams usando anéis do Teams. Esse recurso pode estar disponível anterior ou posterior à atualização do cliente 4.0.105.0

<sup>2</sup> Exige que os administradores de TI ativem Microsoft Whiteboard. Além disso, se você tiver uma tela frontal habilitada para toque, deverá calibrar várias exibições de toque usando as configurações do Windows com logon do administrador do dispositivo para começar a usar Microsoft Whiteboard para colaboração de uma exibição de sala compartilhada em uma reunião do Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introduzido nesta atualização:

- Corrige um problema com o recurso "dar comentários"
- Otimizações em preparação para a próxima atualização do dispositivo Salas do Microsoft Teams para Windows 10 Versão 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introduzido nesta atualização:

- Correção para o bug "suspenso na inicialização do aplicativo" que afetou dispositivos na compilação herdada Windows 10 RS2.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introduzido nesta atualização:

- Teclado DTMF para Microsoft reuniões P2P do Teams e chamadas PSTN. Para tornar Microsoft Teams seu cliente de chamada padrão, os administradores devem definir IsTeamsDefaultClient como true
- Fixar o vídeo de entrada de um participante remoto na tela inteira na frente da exibição da sala. Usar o comando "Pin" da lista de participantes no console
- Melhorias nas notificações do Lobby com adição de notificação da Frente da Sala
- Ícone de conversão de exibição frontal da sala removido quando o sinalizador Bluetooth não está habilitado em Salas do Microsoft Teams dispositivo
- Correção do problema de controle de volume em reuniões do Teams

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introduzido nesta atualização:

- Exibir conteúdo em ambos os displays do FoR (Front of Room) em sistemas de sala de tela dupla
- Temas e melhorias na interface do usuário da Frente da Sala
- Suporte ao cliente do TLS 1.2. Para clientes locais, habilitar a comunicação pelo TLS 1.2 para Salas do Microsoft Teams requer Skype for Business Server CU9 (Atualização Cumulativa 9) ou cu1 (atualização cumulativa 1) de 2015 ou Skype for Business Server 2019 cumulativa 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introduzido nesta atualização:

- Suporte a exibição dupla (Frente de Sala) para Reuniões do Teams

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introduzido nesta atualização:

- Correções de qualidade e confiabilidade

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introduzido nesta atualização:

- Alterações de código necessárias para preparar o aplicativo Salas do Microsoft Teams para atualização posterior Windows 10 versão 1803
- Corrigir o problema de formatação com EULAs localizadas (especificamente norueguês) que impede o avanço além da janela de instalação do EULA OOBE
- Alterações de código necessárias para fazer Salas do Microsoft Teams aplicativo ser executado em sistemas de sala herdados do Lync. Veja mais [aqui](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introduzido nesta atualização:

- O aplicativo Hotfix for Crestron não é iniciado, o que normalmente seria acessível quando o botão do aplicativo em um dispositivo Crestron SR é pressionado. Salas do Microsoft Teams reinicialização do aplicativo necessária após a instalação do 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introduzido nesta atualização:

- Aprimoramentos do recurso "Relatar um problema" no modo teams (equivalente a "Dar Comentários" no modo Skype for Business)
- Habilitar a capacidade de voltar do Teams para o modo Skype for Business para chamadas SIP
- Melhorias de acessibilidade (Narrador, Lupa)
- Reiniciar automaticamente o aplicativo quando necessário após as alterações de provisionamento XML terem sido aplicadas
- Correções diversas

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introduzido nesta atualização:

- Essa atualização permite suporte a reuniões do Skype for Business *e* do Teams em dispositivos de Sistemas de Sala. O Teams é desativado por padrão depois que a atualização é aplicada. Os administradores podem habilitar o Teams localmente nas configurações do dispositivo ou por meio de um push xml remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introduzido nesta atualização:

- Correção para corrigir o erro de endereço observado em alguns sistemas durante o lançamento do aplicativo.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introduzido nesta atualização:

- Alterações que permitem Microsoft gerenciar com mais flexibilidade o Windows Atualizações.
- Nenhuma alteração na experiência do usuário final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introduzido nesta atualização:

- Correção para resolver problemas de capacidade de resposta do console observados em Surface Pro dispositivos baseados em 2017 conectados a duas exibições front-of-room e ingestão de vídeo
- Verificação automatizada para garantir que o sistema esteja executando o script de provisionamento mais recente

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introduzido nesta atualização:

- Correção para melhorar o comportamento do OSK (teclado na tela) nos sistemas baseados na Janela 10 Versão 1709
- Melhorias para se preparar para futuras atualizações do sistema operacional

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introduzido nesta atualização:

- Aplicativo atualizado para melhorar a telemetria

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introduzido nesta atualização:

- Corrige um problema em que podem ocorrer problemas intermitentes de junção de reunião
- Corrige um problema conhecido por resultar em uma experiência de "travamento" do dispositivo

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introduzido nesta atualização:

- Correções de bug/falha para melhorar a estabilidade
- Suporte para console de tamanho variável
- Descarregamento de processamento de áudio periférico (lista de permissões de mídia adicional)
- Otimizações que permitem que os Profissionais de TI criem imagens do -it-yourself com Windows 10 Versão 1709 atualização de janeiro e posterior.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introduzido nesta atualização:

- Corrige um problema com o recurso "Dar Comentários".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introduzido nesta atualização:

- Suporte para hardware de dock [do Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Suporte para o [Logitech Brio](https://www.logitech.com/product/brio)
- Resolve um problema em que as exibições (console e front-of-room) não entram no modo de sono quando não há atividade na sala

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introduzido nesta atualização:

- É executado em um tablet Surface Pro (2017)
- Dá suporte Windows 10 Enterprise Atualização do Criador (idioma inglês, build 1703)
- Suporte para hardware do dock [do Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Suporte OEM para controles de ambiente (Crestron)

A versão de 64 bits do Windows 10 Enterprise Anniversary edition (idioma inglês, versão 1607) não tem mais suporte a partir de Salas do Microsoft Teams versão 3.0.12.0 (atualização 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introduzido nesta atualização:

- Resolve problemas observados ao procurar usuários federados por meio do campo de pesquisa Participantes. Antes dessa correção, os resultados da pesquisa para usuários federados externos podem não ter sido resolvidos corretamente e, em vez disso, retornaram resultados incorretos.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introduzido nesta atualização:

- Dual-Screen suporte (para paridade do sistema herdado)
- Temas (temas internos e a capacidade de definir o tema personalizado)
- Capacidade de dar comentários para builds públicos
- Telemetria aprimorada em torno da confiabilidade da junção da reunião
- Relatórios OMS aprimorados
- Capacidade de Administração de TI para configurar dispositivos remotamente

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introduzido nesta atualização:

- Seleção do usuário no aplicativo de dispositivos USB de áudio e vídeo da sala de reunião
- Relatórios de status do console de sala integrado para clientes usando Microsoft Operations Management Suite, agora Azure Monitor

### <a name="release-to-market-1272016"></a>Lançamento no Mercado (7/12/2016)

**Recursos(s):**

 **Projetado para o Skype for Business**

- Reuniões do Skype com apenas um toque
- Reunião do Skype experiência otimizada para salas com vídeo HD com preenchimento de tela e áudio de banda larga HD
- Todos os participantes podem se conectar à Reunião do Skype usando o dispositivo que quiserem, onde quer que estejam
- Convide pessoas a partir de seu diretório, onde você pode ver imediatamente a disponibilidade de cada contato, ou por chamada telefônica
- Compatível com os recursos de Conferência e Chamada PSTN do Skype for Business para substituir o telefone de conferência em sua sala

 **Transforme qualquer sala de reunião**

- Aplicativo dedicado à Reunião do Skype, otimizado para o controlador de tela touch de centro da mesa e para a grande tela frontal da sala
- Reutilizar investimentos existentes em sua frente de exibição de sala ou projetores
- Funciona para todos os tipos de espaços de reunião, de espaços pequenos a grandes salas de conferência
- Os dispositivos de áudio e vídeo certificados do Skype for Business estão disponíveis para vários tamanhos de sala
- Ingestão integrada com fio para o compartilhamento da área de trabalho do projeto para a sala e para o Reunião do Skype

 **Fácil de implantar, simples de gerenciar**

- Dispositivo always-on que acorda automaticamente os displays quando detecta pessoas na sala
- Implantação e atualização simples do aplicativo de Reunião do Skype da UWP (Plataforma Universal do Windows)
- O Windows AppLocker bloqueia o dispositivo para o aplicativo de Reunião do Skype
- Monitorado e gerenciado como um dispositivo Windows 10 Enterprise por meio de Intune e Configuration Manager (MDM)
- Confiabilidade de nível empresarial
- Esforço mínimo para usuários finais devido à semelhança com a interface do usuário do Skype
- É executado no tablet Surface Pro 4

<a name="See"> </a>
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar seu ambiente](rooms-prep.md)

[Suporte para Salas do Microsoft Teams versões do Branch Atual](rooms-lifecycle-support.md)

[Problemas conhecidos](known-issues.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
