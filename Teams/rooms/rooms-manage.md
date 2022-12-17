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
- Teams_ITAdmin_Rooms
description: Saiba mais sobre como desenvolver e executar operações e manutenção contínuas para garantir que seus sistemas de Salas do Microsoft Teams estejam disponíveis para seus usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 977987cf0283008235a12fdfdda2ffc792c2e289
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438269"
---
# <a name="manage-microsoft-teams-rooms"></a>Gerenciar Salas do Microsoft Teams

Se você tiver Salas do Microsoft Teams em sua organização, terá opções de gerenciamento flexíveis.  Você pode gerenciar os dispositivos por conta própria no mesmo local central em que gerencia todas as soluções do Teams, Microsoft centro de administração do Teams.

Com Microsoft centro de administração do Teams, você pode:

- Executar o gerenciamento de dispositivos como reiniciar dispositivos e baixar logs de dispositivo
- Aplicar configurações específicas do Teams
- Verifique o status de integridade de Salas do Microsoft Teams e seus periféricos, incluindo câmeras, displays, microfones e assim por diante
- Examine a atividade de reunião atual e passada (como detalhes sobre qualidade da chamada, integridade e conectividade da rede e número de participantes)
- Consulte periféricos (como câmeras e projetores) conectados a Salas do Microsoft Teams

Para gerenciar Salas do Teams dispositivos, abra o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) e acesse **Dispositivos** >  do Teams **Salas do Teams no Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Salas do Teams página de resumo no centro de administração do Teams.":::


> [!IMPORTANT]
> Para gerenciar dispositivos usando o centro de administração do Teams, você precisa receber as funções Administrador Global, Administrador do Teams ou Administrador de Dispositivos do Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Fazer alterações em dispositivos Salas do Teams

Se você tiver mais de uma Salas do Teams, poderá fazer a maioria das ações em vários dispositivos ao mesmo tempo. Por exemplo, você pode definir configurações de aplicativo do Teams em todas as suas Salas do Teams ao mesmo tempo.

### <a name="device-settings"></a>Configurações do dispositivo

Você pode alterar as configurações em um ou mais Salas do Teams em sua organização. Para alterar as configurações, selecione o dispositivo ou dispositivos que você deseja gerenciar e selecione **Editar Configurações**. Um novo painel será aberto com todas as configurações que você pode alterar. A tabela a seguir lista as configurações que você pode alterar usando o centro de administração do Teams. Algumas configurações só estão disponíveis quando você seleciona um único Salas do Teams.

Se você selecionar mais de uma, as configurações que dão suporte à edição em massa mostrarão as duas opções a seguir.

- **Manter o valor existente** Se você escolher essa opção, nenhuma alteração será feita na configuração no Salas do Teams selecionado.
- **Substituir o valor existente por** Se você escolher essa opção, poderá atualizar a configuração no Salas do Teams selecionou com o valor fornecido.
    > [!CAUTION]
    > Os valores existentes nas configurações escolhidas para atualizar serão substituídos pelo valor fornecido. Se você quiser adicionar a uma lista de valores existentes, precisará incluir os valores existentes com o valor que deseja adicionar. Por exemplo, se uma configuração tiver uma lista de domínio existente de `contoso.com, fabrikam.com`, e você quiser adicionar `northwindtraders.com`, o valor que você precisa fornecer será `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Se você selecionar várias Salas do Teams, a configuração em todos os dispositivos selecionados será alterada para o valor fornecido. Se Salas do Teams tiver valores diferentes para uma configuração, todos eles serão atualizados para o mesmo valor.

| Configuração                                                      | Valores aceitos                                        | Dá suporte à edição em massa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Conta*                                                    |                                                        |                    |
| **Email**                                                    | Email endereço                                          | Não                 |
| **Modo de reunião com suporte**                                   | somente Microsoft Teams<br>Skype for Business (padrão) e Microsoft Teams<br>Skype for Business e Microsoft Teams (padrão)<br>somente Skype for Business|Sim|
| **Autenticação moderna**                                    | Habilitado<br>Desabilitado                                              | Sim                |
| **Endereço exchange**                                         | Email endereço                                          | Não                 |
| **Domínio\nome de usuário (opcional)**                               | Domínio da conta e nome de usuário                           | Não                 |
| **Configurar domínio**                                         | Lista separada por vírgulas                                   | Sim                |
| *Reuniões*                                                   |                                                        |                    |
| **Compartilhamento automático de tela**                                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Compartilhamento de áudio de ingestão HDMI**                                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Mostrar nomes de reunião**                                       | Habilitado<br>Desabilitado                                              | Sim                |
| **Saída automática se todos os outros saíram da reunião**                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Ingressar em reuniões de terceiros**                 | Cisco Webex<br>Zoom                                              | Sim                |
| **Ingressar com informações de sala**                 | Selecionado<br>Desmarcado                                              | Sim                |
| **Ingressar com informações personalizadas**                 | Selecionado<br>Desmarcado                                              | Sim                |
| **Nome (necessário)**                 | Nome da sala ou espaço                                              | Sim                |
| **Email (necessário)**                 | Email endereço                                              | Sim                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modo de monitor duplo**                                        | Habilitado<br>Desabilitado                                              | Sim                |
| **Permitir duplicação de conteúdo** | Selecionado<br>Desmarcado                                 | Sim                |
| **Baliza bluetooth**                                      | Habilitado<br>Desabilitado                                              | Sim                |
| **Aceitar automaticamente convites de reunião baseados em proximidade** | Selecionado<br>Desmarcado                                 | Sim                |
| **Enviar logs com comentários**                                  | Habilitado<br>Desabilitado                                              | Sim                |
| **Email endereço para logs e comentários**                      | Email endereço                                          | Sim                |
| *Coordenar Reuniões*                                                     |                                                        |                    |
| **Reuniões coordenadas** | Habilitado<br>Desabilitado                                 | Não                |
| **Ativar o microfone deste dispositivo** | Habilitado<br>Desabilitado                                 | Não                |
| **Permitir que as pessoas habilitem ao ingressar em uma reunião** | Selecionado<br>Desmarcado                                 | Não                |
| **Ativar a câmera deste dispositivo** | Habilitado<br>Desabilitado                                 | Não                |
| **Permitir que as pessoas habilitem ao ingressar em uma reunião** | Selecionado<br>Desmarcado                                 | Não                |
| **Ativar o whiteboarding para este dispositivo** | Habilitado<br>Desabilitado                                 | Não                |
| **Contas de dispositivo confiáveis (separadas com vírgulas)** | Lista de dispositivos                              | Não                |
| *Periféricos*                                                |                                                        |                    |
| **Microfone de conferência**                                  | Lista de microfones disponíveis                          | Não                 |
| **Alto-falante de conferência**                                     | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Alto-falante padrão**                                          | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Câmera de conteúdo**                                           | Lista de câmeras disponíveis                              | Não                 |
| **Aprimoramentos da câmera de conteúdo**                              | Habilitado<br>Desabilitado                                              | Não                 |
| **Girar a câmera de conteúdo 180 graus**                        | Habilitado<br>Desabilitado                                              | Não                 |
| *Temas*                                                    |                                                        |                    |
|                                                              | Padrão<br>Nenhum tema<br>Personalizado<br>Lista de temas internos   | Sim                |

### <a name="cortana-settings"></a>Configurações da Cortana

Você pode habilitar a Cortana para _Ativação de Voz_ ou _Push para conversar_ usando o PowerShell para todos os dispositivos da sua organização ou para cada dispositivo separadamente.

Consulte [Salas do Microsoft Teams no Windows](../cortana-in-teams.md) no artigo "Assistência de voz da Cortana no Teams".

### <a name="front-row-layout-settings"></a>Configurações de layout da primeira linha

A primeira linha é a opção de layout de exibição de reunião para Salas do Teams no Windows.

| Dispositivo teams | Versão do aplicativo | Exibição frontal da sala |
|--------------|-------------|-----------------------|
|Salas do Microsoft Teams no Windows | 4.11.12.0 ou superior (a versão mais recente é recomendada) | Dá suporte a exibições individuais e duplas; Tamanho mínimo: 46 polegadas; Proporção 16:9 com resolução 1920x1080 ou 21:9 com resolução 2560x1080; Todas as exibições devem ser definidas em escala de 100% nas configurações do Windows |

Consulte [Salas do Microsoft Teams manutenção e operações](rooms-operations.md#scale-and-resolution) para ajustar as configurações de exibição para atender aos requisitos da primeira linha.

Para saber como definir a primeira linha como o layout padrão de uma sala ou como desativá-la, consulte [Gerenciar uma Salas do Microsoft Teams configurações de console remotamente com um arquivo de configuração XML](xml-config-file.md#set-front-row-as-the-default-layout).

Consulte [Problemas conhecidos](known-issues.md#Limits) para obter mais informações sobre como gerenciar a primeira linha.

## <a name="device-restart-options"></a>Opções de reinicialização do dispositivo

As alterações nas configurações do dispositivo só entrarão em vigor depois que Salas do Teams tiver sido reiniciada. Ao fazer alterações que precisam de uma reinicialização, você pode escolher se deve reiniciar imediatamente ou agendar uma reinicialização. Aqui estão as opções de reinicialização disponíveis:

- **Reinicialização imediata** Se você escolher essa opção, todos os dispositivos aos quais você está fazendo alterações serão reiniciados assim que selecionar essa opção.
- **Reinicialização agendada** Se você escolher essa opção, poderá reiniciar os dispositivos aos quais está fazendo alterações em um momento menos disruptivo para sua organização.
  - **Selecione data e hora** – Escolha a data e a hora específicas para reiniciar o dispositivo. A data e a hora escolhidas são locais para o dispositivo que está sendo reiniciado. 
  - **Deixar atualização para reinicialização noturna** Os dispositivos são reiniciados à noite para executar a manutenção. As alterações feitas em dispositivos serão aplicadas durante essa reinicialização.

> [!CAUTION]
> Salas do Teams que estiverem em uso no momento de uma reinicialização ficarão indisponíveis durante a duração do processo de reinicialização. Eles serão desconectados de reuniões em andamento e não estarão disponíveis para participar de novas reuniões.

## <a name="remove-device"></a>Remover dispositivo

Quando você remove um dispositivo, o dispositivo é removido da sua organização e não aparece mais na sua lista de Salas do Teams no Windows no centro de administração do Teams.

Se você remover um dispositivo e ele ainda estiver configurado com um nome de usuário e senha válidos, ele será adicionado automaticamente à sua lista de Salas do Teams se ele se conectar ao Microsoft 365 novamente.

Para remover um ou mais dispositivos, faça o seguinte:

1. Acesse **Dispositivos** >  do Teams **Salas do Teams no Windows** e selecione os dispositivos que você deseja remover.
2. Selecione **Remover**.

## <a name="download-device-logs"></a>Baixar logs de dispositivo

Você pode baixar uma cópia dos arquivos de log de diagnóstico de um dispositivo se solicitado a fazê-lo Microsoft suporte. Os arquivos de log são compactados em um arquivo zip que pode ser baixado do centro de administração do Teams.

Para baixar logs de um dispositivo Salas do Teams para seu computador, faça o seguinte:

1. Acesse **Dispositivos** >  do Teams **Salas do Teams no Windows** e selecione o nome do dispositivo do qual você deseja baixar logs.
1. Selecione **Baixar logs de dispositivo**. Pode levar vários minutos para que os logs do dispositivo fiquem disponíveis.
1. Selecione a guia **Histórico** e selecione o link do arquivo de log em **Arquivo de diagnóstico**. Um arquivo zip que contém os arquivos de log de diagnóstico do dispositivo será baixado na pasta Downloads padrão do navegador.

## <a name="view-device-information"></a>Exibir informações do dispositivo

No centro de administração do Teams, você pode exibir o status geral de todos os dispositivos em sua organização e exibir detalhes de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>painel do sistema Salas do Teams

O painel do sistema Salas do Teams mostra o status e a integridade de todos os seus dispositivos rapidamente.

### <a name="device-details-view"></a>Exibição de detalhes do dispositivo

Para exibir informações detalhadas sobre um dispositivo, selecione seu nome na lista de dispositivos. Quando estiver na exibição de detalhes, você poderá ver as seguintes informações sobre seu dispositivo:

- **Status de integridade** Mostra a integridade geral do dispositivo Salas do Teams. O status de integridade pode ser **saudável** ou **não saudável**.
- **Offline desde** Mostra a última vez que Microsoft 365 foi capaz de se comunicar com o dispositivo.
- **Status do dispositivo** Mostra o estado atual do dispositivo: **ocioso**, **reunião do Teams**, **reunião do Skype** ou **Ingestão**.
- **Periféricos** Mostra os periféricos conectados ao seu dispositivo Salas do Teams e seu status de integridade. O status de integridade pode ser **conectado** ou **desconectado**.
- **Saúde** Mostra informações detalhadas sobre os periféricos conectados ao seu dispositivo Salas do Teams, conectividade de rede, status de entrada para serviços necessários e informações de versão de software.
- **Detalhes** Mostra informações do fabricante, endereço IP de rede e Salas do Teams endereço serial/MAC do dispositivo.
- **Atividade** Mostra detalhes da reunião anteriores, incluindo data e hora da reunião, número de participantes, duração e qualidade do áudio. Para obter mais informações sobre detalhes da reunião, confira a seção [Detalhes da atividade da reunião](#meeting-activity-details) mais adiante neste artigo.
- **História** Mostra um histórico de atividades de gerenciamento no dispositivo Salas do Teams, incluindo atualizações de configuração, reinicializações de dispositivo e links de download de log de dispositivo.

#### <a name="meeting-activity-details"></a>Detalhes da atividade de reunião

A guia **Atividade** em Salas do Teams detalhes do dispositivo mostra informações de alto nível e detalhadas sobre todas as reuniões em que o dispositivo participou ao longo do tempo. Na guia **Atividade** , você pode ver quando uma reunião foi realizada, quantos participantes participaram da reunião e a qualidade do áudio durante a reunião.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Salas do Teams lista de resumo da atividade do dispositivo.":::

Para ver as informações detalhadas sobre uma reunião específica, selecione a data e a hora da reunião sobre as quais você deseja obter mais informações. Se uma reunião tiver apenas dois participantes, você verá a página de detalhes do participante, caso contrário, verá uma página de resumo do participante.

##### <a name="participant-summary"></a>Resumo do participante

A página de resumo do participante mostra todos os participantes que participaram da reunião. Você pode ver quando cada participante ingressou na reunião, seu nome, qualidade de áudio e quais recursos foram usados durante a sessão. Para exibir os detalhes da sessão de um participante, selecione a hora de início da sessão para esse participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Salas do Teams detalhes da conferência do dispositivo.":::

##### <a name="participant-details"></a>Detalhes do participante

A página de detalhes do participante mostra informações de diagnóstico de ponta a ponta para a sessão desse participante. Conforme mostrado no gráfico a seguir, as informações **de dispositivo**, **sistema** e **conectividade** são fornecidas para o participante e para o dispositivo Salas do Teams. Informações de diagnóstico **de rede** entre o participante e o dispositivo Salas do Teams também são fornecidas. Selecione o ícone para o contexto sobre o qual você deseja obter mais informações. Para obter informações adicionais de diagnóstico, selecione a guia **Avançado** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Salas do Teams detalhes da chamada do dispositivo.":::
