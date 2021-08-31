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
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Saiba mais sobre como desenvolver e executar operações e manutenção contínuas para garantir que seus sistemas Salas do Microsoft Teams estão disponíveis para seus usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ab88563b26faef5be188454126f3bb4df484fe4
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733580"
---
# <a name="manage-microsoft-teams-rooms"></a>Gerenciar Salas do Microsoft Teams

Se você tiver Salas do Microsoft Teams certificados em sua organização, terá opções de gerenciamento flexíveis.  Você pode gerenciar os dispositivos por conta própria no mesmo local central onde gerencia todas as soluções Teams, o Centro de Administração do Microsoft Teams ou pode transferir a responsabilidade de gerenciamento para especialistas dedicados usando Salas do Microsoft Teams [Serviços](https://portal.rooms.microsoft.com)Gerenciados.  Você também pode delegar o acesso de gerenciamento a um parceiro de sua escolha para qualquer uma das opções.

Com Microsoft Teams Admin Center, você pode:

- Executar o gerenciamento de dispositivos, como reiniciar dispositivos e baixar logs de dispositivos
- Aplicar Teams configurações específicas
- Verifique o status de saúde dos Microsoft Teams de sala e seus periféricos, incluindo câmeras, exibições, microfones e assim por diante
- Revise a atividade de reunião atual e passada (como detalhes sobre a qualidade da chamada, a saúde da rede e a conectividade e o número de participantes)
- Consulte periféricos (como câmeras e projetores) conectados a um dispositivo Microsoft Teams Room

Para gerenciar Salas do Teams dispositivos, abra o centro de administração [Microsoft Teams e](https://admin.teams.microsoft.com) vá para   >  **Dispositivos Salas do Teams**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Salas do Teams de resumo no Teams de administração.":::

> [!IMPORTANT]
> Para gerenciar dispositivos usando o Teams de administração, você precisa ter as funções Administrador Global, Administrador Teams administrador ou Teams de Dispositivo.

## <a name="make-changes-to-teams-rooms-devices"></a>Fazer alterações em Salas do Teams dispositivos

Se você tiver mais de um Salas do Teams dispositivo, poderá fazer a maioria das ações em vários dispositivos ao mesmo tempo. Por exemplo, você pode definir Teams configurações do aplicativo em todos os dispositivos ao mesmo tempo.

### <a name="device-settings"></a>Configurações do dispositivo

Você pode alterar as configurações em um ou mais dispositivos em sua organização. Para alterar as configurações, selecione o dispositivo ou dispositivo que você deseja gerenciar e selecione **Editar Configurações**. Um novo painel será aberto com todas as configurações que você pode alterar em seus dispositivos. A tabela a seguir lista as configurações que você pode alterar usando o Teams de administração. Algumas configurações só estão disponíveis quando você seleciona um único dispositivo.

Se você selecionar mais de um dispositivo, as configurações que suportam a edição em massa mostrarão as duas opções a seguir.

- **Manter o valor existente** Se você escolher essa opção, nenhuma alteração será feita na configuração nos dispositivos selecionados.
- **Substituir o valor existente por** Se você escolher essa opção, poderá atualizar a configuração nos dispositivos selecionados com o valor que você fornece.
    > [!CAUTION]
    > Os valores existentes nas configurações que você escolher atualizar serão substituídos pelo valor que você fornecer. Se quiser adicionar a uma lista de valores existentes, você precisará incluir os valores existentes com o valor que deseja adicionar. Por exemplo, se uma configuração tiver uma lista de domínios existente de , e você quiser adicionar , o valor que você precisa `contoso.com, fabrikam.com` `northwindtraders.com` fornecer será `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Se você selecionar vários dispositivos, a configuração em todos os dispositivos selecionados será alterada para o valor que você fornece. Se os dispositivos têm valores diferentes para uma configuração, todos eles serão atualizados para o mesmo valor.

| Configuração                                                      | Valores aceitos                                        | Suporta edição em massa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Conta*                                                    |                                                        |                    |
| **Email**                                                    | Endereço de email                                          | Não                 |
| **Modo de reunião com suporte**                                   | Skype for Business (padrão) e Microsoft Teams<br>Skype for Business e Microsoft Teams (padrão)<br>Skype for Business Somente|Sim|
| **Autenticação moderna**                                    | Habilitado<br>Desabilitado                                              | Sim                |
| **Exchange endereço**                                         | Endereço de email                                          | Não                 |
| **Domínio\nome de usuário (opcional)**                               | Domínio da conta e nome de usuário                           | Não                 |
| **Configurar domínio**                                         | Lista separada por vírgulas                                   | Sim                |
| *Reuniões*                                                   |                                                        |                    |
| **Compartilhamento automático de tela**                                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Mostrar nomes de reunião**                                       | Habilitado<br>Desabilitado                                              | Sim                |
| **Sair automaticamente se todos os outros sairem da reunião**                 | Habilitado<br>Desabilitado                                              | Sim                |
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
| **Aprimoramentos da Câmera de Conteúdo**                              | Habilitado<br>Desabilitado                                              | Não                 |
| **Girar a Câmera de Conteúdo 180 graus**                        | Habilitado<br>Desabilitado                                              | Não                 |
| *Temas*                                                    |                                                        |                    |
|                                                              | Padrão<br>Sem tema<br>Personalizado<br>Lista de temas integrados   | Sim                |

### <a name="device-restart-options"></a>Opções de reinicialização do dispositivo

As alterações nas configurações do dispositivo só terão efeito depois que os dispositivos foram reiniciados. Quando você faz alterações que precisam de uma reinicialização, você pode optar por reiniciar os dispositivos imediatamente ou agendar uma reinicialização. Aqui estão as opções de reinicialização disponíveis:

- **Reinicialização imediata** Se você escolher essa opção, todos os dispositivos para os quais você está fazendo alterações serão reiniciados assim que você selecionar essa opção.
- **Reinicialização agendada** Se você escolher essa opção, poderá reiniciar os dispositivos aos quais está fazendo alterações em um momento menos prejudicial à sua organização.
  - **Selecione data e hora** - Escolha a data e a hora específicas para reiniciar o dispositivo. A data e a hora escolhidas são locais para o dispositivo que está sendo reiniciado. 
  - **Deixar a atualização para reinicialização noturna** Os dispositivos são reiniciados à noite para realizar a manutenção. As alterações feitas em dispositivos serão aplicadas durante essa reinicialização.

> [!CAUTION]
> Os dispositivos em uso no momento de uma reinicialização ficam indisponíveis durante o processo de reinicialização. Eles serão desconectados de reuniões em andamento e não estarão disponíveis para participar de novas reuniões.

### <a name="remove-device"></a>Remover dispositivo

Quando você remove um dispositivo, o dispositivo é removido da sua organização e não aparece mais na sua lista de dispositivos Salas do Teams no centro de administração Teams de segurança.

Se você remover um dispositivo e ele ainda estiver configurado com um nome de usuário e senha válidos, ele será automaticamente adicionado à sua lista de dispositivos Salas do Teams se ele se conectar ao Microsoft 365 novamente.

Para remover um ou mais dispositivos, faça o seguinte:

1. Vá para  >  **Dispositivos Salas do Teams** e selecione os dispositivos que você deseja remover.
1. Selecione **Remover**.

## <a name="download-device-logs"></a>Baixar logs de dispositivo

Você pode baixar uma cópia dos arquivos de log de diagnóstico de um dispositivo, se solicitado pelo suporte da Microsoft. Os arquivos de log são compactados em um arquivo zip que pode ser baixado do Teams de administração.

Para baixar logs de um Salas do Teams para seu computador, faça o seguinte:

1. Vá para **Dispositivos** Salas do Teams e selecione o nome do dispositivo de onde você  >   deseja baixar logs.
1. Selecione **Baixar logs de dispositivo.** Pode levar vários minutos para que os logs de dispositivos se tornem disponíveis.
1. Selecione a **guia Histórico** e selecione o link de arquivo de log em Arquivo **de Diagnóstico.** Um arquivo zip contendo os arquivos de log de diagnóstico do seu dispositivo será baixado para a pasta Downloads padrão do navegador.

## <a name="view-device-information"></a>Exibir informações do dispositivo

No centro de Teams de administração, você pode exibir o status geral de todos os dispositivos em sua organização e exibir detalhes de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Salas do Teams painel do sistema

O Salas do Teams do sistema mostra rapidamente o status e a saúde de todos os dispositivos.

### <a name="device-details-view"></a>Exibição de detalhes do dispositivo

Para exibir informações detalhadas sobre um dispositivo, selecione seu nome na lista de dispositivos. Quando estiver em exibição de detalhes, você poderá ver as seguintes informações sobre seu dispositivo:

- **Status de saúde** Mostra a saúde geral do dispositivo Teams Room. O status de saúde pode ser **healthy** ou **healthyy**.
- **Offline desde** Mostra a última vez Microsoft 365 foi capaz de se comunicar com o dispositivo.
- **Status do dispositivo** Mostra o estado atual do dispositivo: **Idle**, **Teams reunião,** **Skype reunião** ou **Ingest**.
- **Periféricos** Mostra os periféricos conectados ao seu dispositivo Teams Room e seu status de saúde. O status de saúde pode ser **conectado** ou **desconectado.**
- **Saúde** Mostra informações detalhadas sobre os periféricos conectados ao seu dispositivo de sala Teams, conectividade de rede, status de entrada para serviços necessários e informações de versão de software.
- **Detalhes** Mostra informações do fabricante, endereço IP de rede e Teams endereço serial/MAC do dispositivo de sala.
- **Atividade** Mostra detalhes da reunião passada, incluindo data e hora da reunião, número de participantes, duração e qualidade de áudio. Para obter mais informações sobre detalhes da reunião, consulte a seção Detalhes da atividade [de](#meeting-activity-details) reunião mais adiante neste artigo.
- **Histórico** Mostra um histórico de atividades de gerenciamento no dispositivo Teams Room, incluindo atualizações de configuração, reinicializações de dispositivos e links de download de log de dispositivo.

#### <a name="meeting-activity-details"></a>Detalhes da atividade de reunião

A **guia Atividade** Teams detalhes do dispositivo room mostra informações detalhadas e de alto nível sobre todas as reuniões das que o dispositivo participou ao longo do tempo. Na guia **Atividade,** você pode ver quando uma reunião foi realizada, quantos participantes participaram da reunião e a qualidade do áudio durante a reunião.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Lista de resumos de atividades do dispositivo de sala.":::

Para ver as informações detalhadas sobre uma reunião específica, selecione a data e a hora da reunião de que você deseja obter mais informações. Se uma reunião tiver apenas dois participantes, você verá a página de detalhes do participante, caso contrário, você verá uma página de resumo do participante.

##### <a name="participant-summary"></a>Resumo do participante

A página de resumo do participante mostra todos os participantes que participaram da reunião. Você pode ver quando cada participante ingressou na reunião, seu nome, qualidade de áudio e quais recursos foram usados durante a sessão. Para exibir os detalhes da sessão de um participante, selecione a hora de início da sessão para esse participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams Detalhes da conferência do dispositivo de sala.":::

##### <a name="participant-details"></a>Detalhes do participante

A página de detalhes do participante mostra informações de diagnóstico de ponta a ponta para a sessão desse participante. Conforme mostrado no gráfico a seguir,  as informações de **Dispositivo,** Sistema e Conectividade são fornecidas para o participante e para o Salas do Teams dispositivo. **Informações** de diagnóstico de rede entre o participante e o Salas do Teams dispositivo também são fornecidas. Selecione o ícone do contexto sobre o qual você deseja obter mais informações. Para obter informações de diagnóstico adicionais, selecione a **guia** Avançado.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams Detalhes da chamada do dispositivo de sala.":::
