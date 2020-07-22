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
description: Saiba mais sobre como desenvolver e executar manutenção e operações contínuas para garantir que seus sistemas de salas do Microsoft Teams estejam disponíveis para seus usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2339967d6d7705266c13dbc65fb689c49c8e8279
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202917"
---
# <a name="manage-microsoft-teams-rooms"></a>Gerenciar Salas do Microsoft Teams

Se você tiver dispositivos certificados da Microsoft Teams em sua organização, poderá gerenciá-los em um local central usando o centro de administração do Microsoft Teams. Você pode:

- Executar o gerenciamento de dispositivos, como reinicializar ou bloquear dispositivos e baixar logs de dispositivos
- Aplicar configurações específicas de equipes
- Verifique o status de integridade dos dispositivos de sala do Microsoft Teams e seus periféricos, incluindo câmeras, monitores, microfones e assim por diante
- Revisar a atividade atual e anterior da reunião (como detalhes sobre a qualidade da chamada, a integridade e a conectividade da rede e o número de participantes)
- Ver periféricos (como câmeras e projetores) conectados a um dispositivo da sala do Microsoft Teams

Para gerenciar dispositivos de salas de equipe, abra o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) e vá para salas de equipe de **dispositivos**  >  **Teams Rooms**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Páginas de Resumo de salas de equipe no centro de administração do teams":::

> [!IMPORTANT]
> Para gerenciar dispositivos usando o centro de administração do Teams, você precisa receber as funções de administrador do teams Service ou administrador global.

## <a name="make-changes-to-teams-rooms-devices"></a>Fazer alterações em dispositivos de salas de equipe

Se você tiver mais de um dispositivo de salas de equipe, poderá fazer a maioria das ações em vários dispositivos ao mesmo tempo. Por exemplo, você pode definir as configurações do aplicativo Teams em todos os seus dispositivos ao mesmo tempo.

### <a name="device-settings"></a>Configurações do dispositivo

Você pode alterar as configurações em um ou mais dispositivos em sua organização. Para alterar as configurações, selecione o dispositivo ou dispositivos que você deseja gerenciar e, em seguida, selecione **Editar configurações**. Um novo painel será aberto com todas as configurações que você pode alterar em seus dispositivos. A tabela a seguir lista as configurações que você pode alterar usando o centro de administração do teams. Algumas configurações só estão disponíveis quando você seleciona um único dispositivo.

Se você selecionar mais de um dispositivo, as configurações que dão suporte a edição em massa mostram as duas opções a seguir.

- **Manter valor existente** Se você escolher essa opção, nenhuma alteração será feita na configuração dos dispositivos que você selecionou.
- **Substituir valor existente por** Se você escolher essa opção, poderá atualizar a configuração nos dispositivos que você selecionou com o valor fornecido.
    > [!CAUTION]
    > Os valores existentes nas configurações que você escolher para atualizar serão substituídos pelo valor que você fornecer. Se quiser adicionar a uma lista de valores existentes, você precisará incluir os valores existentes com o valor que você deseja adicionar. Por exemplo, se uma configuração tiver uma lista de domínios existente `contoso.com, fabrikam.com` e você quiser adicioná- `northwindtraders.com` la, o valor que você precisará fornecer será `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Se você selecionar vários dispositivos, a configuração em todos os dispositivos que você selecionar será alterada para o valor que você fornecer. Se os dispositivos tiverem valores diferentes para uma configuração, eles serão atualizados para o mesmo valor.

| Configuração                                                      | Valores aceitos                                        | Suporte para edição em massa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Conta*                                                    |                                                        |                    |
| **Email**                                                    | Endereço de email                                          | Não                 |
| **Modo de reunião compatível**                                   | Skype for Business (padrão) e Microsoft Teams<br>Skype for Business e Microsoft Teams (padrão)<br>Somente Skype for Business|Sim|
| **Autenticação moderna**                                    | Ativado<br>Desativado                                              | Sim                |
| **Endereço do Exchange**                                         | Endereço de email                                          | Não                 |
| **Domínio \ nome_de_usuário (opcional)**                               | Domínio da conta e nome de usuário                           | Não                 |
| **Configurar domínio**                                         | Lista separada por vírgulas                                   | Sim                |
| *Reuniões*                                                   |                                                        |                    |
| **Compartilhamento automático de tela**                                 | Ativado<br>Desativado                                              | Sim                |
| **Mostrar nomes de reuniões**                                       | Ativado<br>Desativado                                              | Sim                |
| **Sair automaticamente se outras pessoas saíram da reunião**                 | Ativado<br>Desativado                                              | Sim                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modo de monitor duplo**                                        | Ativado<br>Desativado                                              | Sim                |
| **Beaconing Bluetooth**                                      | Ativado<br>Desativado                                              | Sim                |
| **Aceitar automaticamente convites para reunião baseados em proximidade** | Selecionado<br>Não selecionada                                 | Sim                |
| **Enviar logs com comentários**                                  | Ativado<br>Desativado                                              | Sim                |
| **Endereço de email para logs e comentários**                      | Endereço de email                                          | Sim                |
| *Periféricos*                                                |                                                        |                    |
| **Microfone de conferência**                                  | Lista de microfones disponíveis                          | Não                 |
| **Palestrante de conferência**                                     | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Alto-falante padrão**                                          | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Câmera de conteúdo**                                           | Lista de câmeras disponíveis                              | Não                 |
| **Aprimoramentos da câmera de conteúdo**                              | Ativado<br>Desativado                                              | Não                 |
| **Girar o conteúdo da câmera 180 graus**                        | Ativado<br>Desativado                                              | Não                 |
| *Temas*                                                    |                                                        |                    |
|                                                              | Padrão<br>Sem tema<br>Personalizado<br>Lista de temas internos   | Sim                |

### <a name="device-restart-options"></a>Opções de reinicialização de dispositivo

As alterações nas configurações do dispositivo só entrarão em vigor depois que os dispositivos forem reiniciados. Ao fazer alterações que precisem de uma reinicialização, você pode escolher se deseja reiniciar os dispositivos imediatamente ou agendar uma reinicialização. Estas são as opções de reinicialização disponíveis:

- **Reinício imediato** Se você escolher essa opção, todos os dispositivos que está fazendo alterações serão reiniciados assim que você selecionar essa opção.
- **Reinício agendado** Se você escolher essa opção, poderá reiniciar os dispositivos nos quais está fazendo alterações de uma vez, o que faz menos interrupções na sua organização.
  - **Selecionar data e hora** -escolha a data e a hora específicas para reiniciar o dispositivo. A data e a hora que você escolher são locais para o dispositivo que está sendo reiniciado. 
  - **Sair da atualização para a reinicialização noturna** Os dispositivos são reiniciados à noite para executar a manutenção. As alterações feitas em dispositivos serão aplicadas durante essa reinicialização.

> [!CAUTION]
> Os dispositivos em uso no momento em que a reinicialização se tornarão indisponíveis durante o processo de reinicialização. Eles serão desconectados de reuniões em andamento e não estarão disponíveis para ingressar em novas reuniões.

### <a name="remove-or-block-a-device"></a>Remover ou bloquear um dispositivo

Quando você **Remove** um dispositivo, o dispositivo é removido da sua organização e não é mais exibido na sua lista de dispositivos de salas de equipe no centro de administração do teams. 

Quando você **bloqueia** um dispositivo, as equipes não se comunicam mais com o dispositivo. Os dispositivos bloqueados não serão enviados para os comandos mesmo se estiverem incluídos em um grupo de dispositivos que estejam sendo editados em massa. Ela ainda está listada na sua lista de dispositivos de salas de equipe com um status de **bloqueado**.

Não importa se um dispositivo está bloqueado ou removido, se ainda está configurado com um nome de usuário e senha válidos, ele será automaticamente readicionado à sua lista de dispositivos de salas de equipe se ele se conectar ao Microsoft 365.

Para remover um ou mais dispositivos, faça o seguinte:

1. Vá para **Devices**  >  **salas de equipe** de dispositivos e selecione os dispositivos que você deseja remover.
1. Selecione **Remover**.

Para bloquear um dispositivo, faça o seguinte:

1. Vá para **Devices**  >  **salas de equipe** de dispositivos e selecione o nome do dispositivo que você deseja bloquear.
1. Na página detalhes do dispositivo, selecione **ações** no canto superior direito da página.
1. Selecione **Bloquear**.

Para desbloquear um dispositivo, faça o seguinte:

1. Vá para **Devices**  >  **salas de equipe** de dispositivos e selecione o nome do dispositivo que você deseja bloquear.
1. Na página detalhes do dispositivo, selecione **ações** no canto superior direito da página.
1. Selecione **desbloquear**.

## <a name="download-device-logs"></a>Baixar logs de dispositivo

Você pode baixar uma cópia dos arquivos de log de diagnóstico de um dispositivo, se for solicitado pelo suporte da Microsoft. Os arquivos de log são compactados em um arquivo zip que pode ser baixado no centro de administração do teams.

Para baixar logs de um dispositivo de salas de equipe para o seu computador, faça o seguinte:

1. Vá para **Devices**  >  **salas de equipe** de dispositivos e selecione o nome do dispositivo do qual você deseja baixar logs.
1. Selecione **baixar logs de dispositivo**. Pode levar alguns minutos para que os logs do dispositivo fiquem disponíveis.
1. Selecione a guia **histórico** e, em seguida, selecione o link arquivo de log em **arquivo de diagnóstico**. Um arquivo zip que contém os arquivos de log de diagnóstico do seu dispositivo será baixado para a pasta de downloads padrão do seu navegador.

## <a name="view-device-information"></a>Exibir informações do dispositivo

No centro de administração do Teams, você vê o status geral de todos os dispositivos em sua organização e exibe os detalhes de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Painel de sistema de salas de equipe

O painel de sistema salas de equipe mostra o status e a integridade de todos os seus dispositivos em um relance.

### <a name="device-details-view"></a>Exibição de detalhes do dispositivo

Para ver informações detalhadas sobre um dispositivo, selecione seu nome na lista de dispositivos. No modo de exibição de detalhes, você pode ver as seguintes informações sobre o seu dispositivo:

- **Status de integridade** Mostra a integridade geral do dispositivo da sala de equipes. O status de integridade pode ser **íntegro** ou não **íntegro**.
- **Offline desde** Mostra a última vez que o Microsoft 365 pôde se comunicar com o dispositivo.
- **Status do dispositivo** Mostra o estado atual do dispositivo: **ocioso**, **reunião do teams**, **reunião do Skype**ou **recebimento**.
- **Periféricos** Mostra os periféricos conectados ao dispositivo da sala de equipes e seu status de integridade. O status de integridade pode ser **conectado** ou **desconectado**.
- **Integridade** do Mostra informações detalhadas sobre os periféricos conectados ao dispositivo de sala de equipes, conectividade de rede, status de entrada para serviços necessários e informações sobre a versão do software.
- **Detalhes** do Mostra as informações do fabricante, o endereço IP da rede e o endereço serial/MAC do dispositivo da sala de equipe.
- **Atividade** do Mostra os detalhes da reunião passada, incluindo data e hora da reunião, número de participantes, duração e qualidade de áudio. Para obter mais informações sobre os detalhes da reunião, consulte a seção [detalhes da atividade da reunião](#meeting-activity-details) , mais adiante neste artigo.
- **Histórico** de Mostra um histórico de atividades de gerenciamento no dispositivo da sala de equipes, incluindo atualizações de configuração, reinicializações de dispositivo e links de download de log de dispositivo.

#### <a name="meeting-activity-details"></a>Detalhes da atividade da reunião

A guia **atividade** nos detalhes do dispositivo da sala de equipes mostra informações detalhadas e de alto nível sobre todas as reuniões nas quais o dispositivo participou ao longo do tempo. Na guia **atividade** , você pode ver quando uma reunião foi mantida, quantos participantes participaram da reunião e a qualidade do áudio durante a reunião.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Lista Resumo de atividade do dispositivo da sala de equipes":::

Para ver as informações detalhadas sobre uma reunião específica, selecione a data e a hora da reunião sobre a qual você deseja obter mais informações. Se uma reunião tiver apenas dois participantes, você verá a página de detalhes do participante, caso contrário, verá uma página de resumo do participante.

##### <a name="participant-summary"></a>Resumo de participantes

A página Resumo do participante mostra todos os participantes que participaram da reunião. Você pode ver quando cada participante ingressou na reunião, o nome dela, a qualidade de áudio e quais recursos foram usados durante a sessão. Para exibir os detalhes da sessão de um participante, selecione a hora de início da sessão do participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Detalhes da conferência do dispositivo da sala de equipes":::

##### <a name="participant-details"></a>Detalhes do participante

A página detalhes do participante mostra as informações de diagnóstico de ponta a ponta para a sessão do participante. Conforme mostrado nas informações de elemento gráfico, **dispositivo**, **sistema**e **conectividade** a seguir é fornecida para o participante e para o dispositivo de salas de equipe. As informações de diagnóstico de **rede** entre o participante e o dispositivo de salas de equipe também são fornecidas. Selecione o ícone do contexto sobre o qual você deseja obter mais informações. Para obter informações adicionais de diagnóstico, selecione a guia **avançado** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Detalhes da chamada de dispositivos da sala de equipe":::
