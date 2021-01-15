---
title: Gerenciar Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Saiba mais sobre como desenvolver e executar operações e manutenção contínuas para garantir que seus sistemas de Salas do Microsoft Teams estão disponíveis para seus usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 830caffbbb0256e64198e84876a4067337e90266
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848833"
---
# <a name="manage-microsoft-teams-rooms"></a>Gerenciar Salas do Microsoft Teams

Se você tiver dispositivos certificados para Salas do Microsoft Teams em sua organização, terá opções de gerenciamento flexíveis.  Você pode gerenciar os dispositivos por conta própria no mesmo local central onde gerencia todas as soluções do Teams, centro de administração do Microsoft Teams ou transferir a responsabilidade de gerenciamento para especialistas dedicados usando os Serviços Gerenciados de Salas do [Microsoft Teams.](https://portal.rooms.microsoft.com)  Você também pode delegar o acesso de gerenciamento a um parceiro de sua escolha para qualquer uma das opções.

Com o Centro de administração do Microsoft Teams, você pode:

- Executar o gerenciamento de dispositivos, como reiniciar ou bloquear dispositivos e baixar logs de dispositivos
- Aplicar configurações específicas do Teams
- Verifique o status de saúde dos dispositivos da Sala do Microsoft Teams e seus periféricos, incluindo câmeras, telas, microfones e assim por diante
- Revise as atividades atuais e passadas da reunião (como detalhes sobre a qualidade da chamada, a conectividade e a saúde da rede e o número de participantes)
- Ver periféricos (como câmeras e projetores) conectados a um dispositivo de sala do Microsoft Teams

Para gerenciar dispositivos de Salas do Teams, abra o centro [de administração do Microsoft Teams](https://admin.teams.microsoft.com) e vá para Salas **do** Teams de  >  **Dispositivos.**

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Páginas de resumo de Salas do Teams no Centro de administração do Teams":::

> [!IMPORTANT]
> Para gerenciar dispositivos usando o centro de administração do Teams, você precisa ter as funções Administrador Global, Administrador de Serviço do Teams ou Administrador de Dispositivos do Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Fazer alterações em dispositivos de Salas do Teams

Se você tiver mais de um dispositivo de Salas do Teams, poderá fazer a maioria das ações em vários dispositivos ao mesmo tempo. Por exemplo, você pode definir configurações de aplicativos do Teams em todos os seus dispositivos ao mesmo tempo.

### <a name="device-settings"></a>Configurações do dispositivo

Você pode alterar as configurações em um ou mais dispositivos em sua organização. Para alterar as configurações, selecione o dispositivo ou dispositivo que você deseja gerenciar e selecione **Editar Configurações.** Um novo painel será aberto com todas as configurações que você pode alterar em seus dispositivos. A tabela a seguir lista as configurações que você pode alterar usando o centro de administração do Teams. Algumas configurações só estarão disponíveis quando você selecionar um único dispositivo.

Se você selecionar mais de um dispositivo, as configurações que suportam edição em massa mostrarão as duas opções a seguir.

- **Manter o valor existente** Se você escolher essa opção, nenhuma alteração será feita na configuração nos dispositivos selecionados.
- **Substituir o valor existente por** Se você escolher essa opção, poderá atualizar a configuração nos dispositivos selecionados com o valor que forneceu.
    > [!CAUTION]
    > Os valores existentes nas configurações que você escolher atualizar serão substituídos pelo valor que você fornecer. Se quiser adicionar a uma lista de valores existentes, você precisará incluir os valores existentes com o valor que deseja adicionar. Por exemplo, se uma configuração tiver uma lista de domínios existente de , e você deseja adicionar , o valor que você precisa `contoso.com, fabrikam.com` `northwindtraders.com` fornecer seria `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Se você selecionar vários dispositivos, a configuração em todos os dispositivos selecionados será alterada para o valor que você fornecer. Se os dispositivos têm valores diferentes para uma configuração, todos eles serão atualizados para o mesmo valor.

| Configuração                                                      | Valores aceitos                                        | Oferece suporte à edição em massa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Conta*                                                    |                                                        |                    |
| **Email**                                                    | Endereço de email                                          | Não                 |
| **Modo de reunião com suporte**                                   | Skype for Business (padrão) e Microsoft Teams<br>Skype for Business e Microsoft Teams (padrão)<br>Somente Skype for Business|Sim|
| **Autenticação moderna**                                    | Habilitado<br>Desabilitado                                              | Sim                |
| **Endereço do Exchange**                                         | Endereço de email                                          | Não                 |
| **Domínio\nome de usuário (opcional)**                               | Domínio da conta e nome de usuário                           | Não                 |
| **Configurar domínio**                                         | Lista separada por vírgulas                                   | Sim                |
| *Reuniões*                                                   |                                                        |                    |
| **Compartilhamento automático de tela**                                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Mostrar nomes de reunião**                                       | Habilitado<br>Desabilitado                                              | Sim                |
| **Saída automática se todos os outros sairem da reunião**                 | Habilitado<br>Desabilitado                                              | Sim                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modo de monitor duplo**                                        | Habilitado<br>Desabilitado                                              | Sim                |
| **Bluetooth sinalizador**                                      | Habilitado<br>Desabilitado                                              | Sim                |
| **Aceitar automaticamente convites de reunião baseados em proximidade** | Selecionado<br>Unselected                                 | Sim                |
| **Enviar logs com comentários**                                  | Habilitado<br>Desabilitado                                              | Sim                |
| **Endereço de email para logs e comentários**                      | Endereço de email                                          | Sim                |
| *Periféricos*                                                |                                                        |                    |
| **Microfone de conferência**                                  | Lista de microfones disponíveis                          | Não                 |
| **Alto-falante de conferência**                                     | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Alto-falante padrão**                                          | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Câmera de conteúdo**                                           | Lista de câmeras disponíveis                              | Não                 |
| **Aprimoramentos da câmera de conteúdo**                              | Habilitado<br>Desabilitado                                              | Não                 |
| **Girar a Câmera de Conteúdo 180 graus**                        | Habilitado<br>Desabilitado                                              | Não                 |
| *Temas*                                                    |                                                        |                    |
|                                                              | Padrão<br>Sem tema<br>Personalizado<br>Lista de temas integrados   | Sim                |

### <a name="device-restart-options"></a>Opções de reinicialização do dispositivo

As alterações nas configurações do dispositivo só terão efeito após a reinicialização dos dispositivos. Ao fazer alterações que precisam de uma reinicialização, você pode optar por reiniciar os dispositivos imediatamente ou agendar uma reinicialização. Aqui estão as opções de reinicialização disponíveis:

- **Reinicialização imediata** Se você escolher essa opção, todos os dispositivos para os quais você está fazendo alterações serão reiniciados assim que você selecionar essa opção.
- **Reinicialização agendada** Se você escolher essa opção, poderá reiniciar os dispositivos para os quais está fazendo alterações em um momento que seja menos prejudicial à sua organização.
  - **Selecionar data e hora** - Escolha a data e a hora específicas para reiniciar o dispositivo. A data e a hora que você escolher é local para o dispositivo que está sendo reiniciado. 
  - **Deixar a atualização para reinicialização noturna** Os dispositivos são reiniciados à noite para realizar a manutenção. As alterações feitas em dispositivos serão aplicadas durante essa reinicialização.

> [!CAUTION]
> Os dispositivos em uso no momento de uma reinicialização se tornarão indisponíveis durante o processo de reinicialização. Eles serão desconectados de reuniões em andamento e não estarão disponíveis para ingressar em novas reuniões.

### <a name="remove-or-block-a-device"></a>Remover ou bloquear um dispositivo

Quando você **remove** um dispositivo, o dispositivo é removido da sua organização e não aparece mais na sua lista de dispositivos de Salas do Teams no centro de administração do Teams. 

Quando você **bloqueia um** dispositivo, o Teams não se comunica mais com o dispositivo. Os dispositivos bloqueados não serão enviados comandos mesmo se eles estão incluídos em um grupo de dispositivos que estão sendo editados em massa. Ele ainda está listado em sua lista de dispositivos de Salas do Teams com o status **bloqueado.**

Independentemente de um dispositivo ser bloqueado ou removido, se ele ainda estiver configurado com um nome de usuário e senha válidos, ele será automaticamente adicionado à sua lista de dispositivos de Salas do Teams se ele se conectar ao Microsoft 365.

Para remover um ou mais dispositivos, faça o seguinte:

1. Vá para **Salas do**  >  **Teams de** Dispositivos e selecione os dispositivos que você deseja remover.
1. Selecione **Remover**.

Para bloquear um dispositivo, faça o seguinte:

1. Vá para **Salas do**  >  **Teams de** Dispositivos e selecione o nome do dispositivo que você deseja bloquear.
1. Na página de detalhes do dispositivo, selecione **Ações** no canto superior direito da página.
1. Selecione **Bloquear**.

Para desbloquear um dispositivo, faça o seguinte:

1. Vá para **Salas do**  >  **Teams de** Dispositivos e selecione o nome do dispositivo que você deseja bloquear.
1. Na página de detalhes do dispositivo, selecione **Ações** no canto superior direito da página.
1. Selecione **Desbloquear**.

## <a name="download-device-logs"></a>Baixar logs de dispositivos

Você pode baixar uma cópia dos arquivos de log de diagnóstico de um dispositivo, se solicitado pelo suporte da Microsoft. Os arquivos de log são compactados em um arquivo zip que pode ser baixado do Centro de administração do Teams.

Para baixar logs de um dispositivo de Salas do Teams para seu computador, faça o seguinte:

1. Vá para **Salas do** Teams de Dispositivos e selecione o nome do dispositivo em que você deseja baixar  >   logs.
1. Selecione **Baixar logs de dispositivo.** Pode levar vários minutos para que os logs de dispositivos se tornem disponíveis.
1. Selecione a **guia Histórico** e selecione o link do arquivo de log em Arquivo **de Diagnóstico.** Um arquivo zip que contém os arquivos de log de diagnóstico do dispositivo será baixado para a pasta Downloads padrão do navegador.

## <a name="view-device-information"></a>Exibir informações do dispositivo

No centro de administração do Teams, você pode exibir o status geral de todos os dispositivos em sua organização e exibir detalhes de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Painel do sistema salas do Teams

O painel do sistema salas do Teams mostra o status e a saúde de todos os seus dispositivos rapidamente.

### <a name="device-details-view"></a>Exibição de detalhes do dispositivo

Para exibir informações detalhadas sobre um dispositivo, selecione seu nome na lista de dispositivos. Quando na exibição de detalhes, você pode ver as seguintes informações sobre seu dispositivo:

- **Status de saúde** Mostra a saúde geral do dispositivo de Sala do Teams. O status de saúde pode ser **Healthy** ou **Unhealthy**.
- **Offline desde** Mostra a última vez que o Microsoft 365 conseguiu se comunicar com o dispositivo.
- **Status do dispositivo** Mostra o estado atual do dispositivo: **Ocioso**, **reunião do Teams,** **reunião do Skype** ou **Ingestão.**
- **Periféricos** Mostra os periféricos conectados ao dispositivo de Sala do Teams e seu status de saúde. O status de saúde pode **ser Conectado** ou **Desconectado.**
- **Health** Mostra informações detalhadas sobre os periféricos conectados ao seu dispositivo de Sala do Teams, conectividade de rede, status de entrada para serviços necessários e informações de versão de software.
- **Detalhes** Mostra informações do fabricante, endereço IP de rede e endereço SERIAL/MAC do dispositivo da Sala do Teams.
- **Atividade** Mostra detalhes da reunião anteriores, incluindo data e hora da reunião, número de participantes, duração e qualidade de áudio. Para obter mais informações sobre detalhes da reunião, consulte a seção de detalhes da [atividade de](#meeting-activity-details) reunião mais adiante neste artigo.
- **Histórico** Mostra um histórico de atividade de gerenciamento no dispositivo de Sala do Teams, incluindo atualizações de configuração, reinicializações de dispositivos e links de download de log de dispositivo.

#### <a name="meeting-activity-details"></a>Detalhes da atividade da reunião

A **guia Atividade** nos detalhes do dispositivo da Sala do Teams mostra informações detalhadas e de alto nível sobre todas as reuniões das que o dispositivo participou ao longo do tempo. Na guia **Atividade,** você pode ver quando uma reunião foi realizada, quantos participantes participaram da reunião e a qualidade do áudio durante a reunião.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Lista de resumo de atividades do dispositivo de sala do Teams":::

Para ver as informações detalhadas sobre uma reunião específica, selecione a data e a hora da reunião sobre as que você deseja obter mais informações. Se uma reunião tiver apenas dois participantes, você verá a página de detalhes do participante; caso contrário, você verá uma página de resumo do participante.

##### <a name="participant-summary"></a>Resumo do participante

A página de resumo do participante mostra todos os participantes que participaram da reunião. Você pode ver quando cada participante ingressou na reunião, seu nome, qualidade de áudio e quais recursos foram usados durante a sessão. Para exibir os detalhes da sessão de um participante, selecione a hora de início da sessão para esse participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Detalhes da conferência do dispositivo de sala do Teams":::

##### <a name="participant-details"></a>Detalhes do participante

A página de detalhes do participante mostra informações de diagnóstico de ponta a ponta para a sessão desse participante. Conforme mostrado no gráfico a seguir,  as informações de **Dispositivo,** **Sistema** e Conectividade são fornecidas para o participante e para o dispositivo salas do Teams. **As informações** de diagnóstico de rede entre o participante e o dispositivo salas do Teams também são fornecidas. Selecione o ícone do contexto sobre o qual você deseja obter mais informações. Para obter informações de diagnóstico adicionais, selecione **a guia** Avançado.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Detalhes da chamada do dispositivo de sala do Teams":::
