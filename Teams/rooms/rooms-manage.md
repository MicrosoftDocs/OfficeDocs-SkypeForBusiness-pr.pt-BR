---
title: Gerenciar Salas do Microsoft Teams
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
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Saiba mais sobre como desenvolver e executar operações e manutenção contínuas para garantir que seus sistemas Salas do Microsoft Teams estejam disponíveis para seus usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47f1c170fd0c41331dfaffa2d81386ac3c2fb722
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106266"
---
# <a name="manage-microsoft-teams-rooms"></a>Gerenciar Salas do Microsoft Teams

Se você tiver Salas do Microsoft Teams em sua organização, terá opções de gerenciamento flexíveis.  Você pode gerenciar os dispositivos por conta própria no mesmo local central em que gerencia todas as soluções Teams, Microsoft Teams de administração. Como alternativa, você pode transferir a responsabilidade de gerenciamento para especialistas dedicados [usando Salas do Microsoft Teams Serviços Gerenciados](https://portal.rooms.microsoft.com).  Você também pode delegar acesso de gerenciamento a um parceiro de sua escolha para qualquer uma das opções.

Com Microsoft Teams de administração, você pode:

- Executar o gerenciamento de dispositivos, como reiniciar dispositivos e baixar logs de dispositivos
- Aplicar Teams configurações específicas
- Verifique o status de integridade Salas do Microsoft Teams e seus periféricos, incluindo câmeras, telas, microfones e assim por diante
- Examine as atividades atuais e anteriores da reunião (como detalhes sobre a qualidade da chamada, a integridade da rede e a conectividade e o número de participantes)
- Ver periféricos (como câmeras e projetores) conectados Salas do Microsoft Teams

Para gerenciar Salas do Teams, abra o centro [de administração Microsoft Teams](https://admin.teams.microsoft.com) e vá para Teams **Dispositivos** >  **Salas do Teams no Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Salas do Teams de resumo no Teams de administração.":::


> [!IMPORTANT]
> Para gerenciar dispositivos usando o Teams de administração, você precisa receber as funções administrador global, administrador Teams ou administrador Teams dispositivos.

## <a name="make-changes-to-teams-rooms-devices"></a>Fazer alterações em Salas do Teams dispositivos

Se você tiver mais de um Salas do Teams, poderá executar a maioria das ações em vários dispositivos ao mesmo tempo. Por exemplo, você pode definir Teams configurações do aplicativo em todas as suas Salas do Teams ao mesmo tempo.

### <a name="device-settings"></a>Configurações do dispositivo

Você pode alterar as configurações em um ou mais Salas do Teams em sua organização. Para alterar as configurações, selecione o dispositivo ou os dispositivos que você deseja gerenciar e, em seguida, selecione **Editar Configurações**. Um novo painel será aberto com todas as configurações que você pode alterar. A tabela a seguir lista as configurações que você pode alterar usando o Teams de administração. Algumas configurações só estão disponíveis quando você seleciona um único Salas do Teams.

Se você selecionar mais de uma, as configurações que dão suporte à edição em massa mostrarão as duas opções a seguir.

- **Manter o valor existente** Se você escolher essa opção, nenhuma alteração será feita na configuração Salas do Teams você selecionou.
- **Substituir o valor existente por** Se você escolher essa opção, poderá atualizar a configuração no Salas do Teams selecionado com o valor fornecido.
    > [!CAUTION]
    > Os valores existentes nas configurações que você escolher atualizar serão substituídos pelo valor fornecido. Se você quiser adicionar a uma lista de valores existentes, precisará incluir os valores existentes com o valor que deseja adicionar. Por exemplo, se uma configuração tiver uma lista `contoso.com, fabrikam.com``northwindtraders.com`de domínios existente e você quiser adicionar, o valor que você precisa fornecer será `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Se você selecionar várias Salas do Teams, a configuração em todos os dispositivos selecionados será alterada para o valor fornecido. Se Salas do Teams tiver valores diferentes para uma configuração, todos eles serão atualizados para o mesmo valor.

| Configuração                                                      | Valores aceitos                                        | Dá suporte à edição em massa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Conta*                                                    |                                                        |                    |
| **Email**                                                    | Endereço de email                                          | Não                 |
| **Modo de reunião com suporte**                                   | Microsoft Teams<br>Skype for Business (padrão) e Microsoft Teams<br>Skype for Business e Microsoft Teams (padrão)<br>Skype for Business|Sim|
| **Autenticação moderna**                                    | Habilitado<br>Desabilitado                                              | Sim                |
| **Exchange endereço**                                         | Endereço de email                                          | Não                 |
| **Domínio\nome de usuário (opcional)**                               | Nome de usuário e domínio da conta                           | Não                 |
| **Configurar domínio**                                         | Lista separada por vírgulas                                   | Sim                |
| *Reuniões*                                                   |                                                        |                    |
| **Compartilhamento automático de tela**                                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Compartilhamento de áudio de ingestão de HDMI**                                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Mostrar nomes de reunião**                                       | Habilitado<br>Desabilitado                                              | Sim                |
| **Sair automaticamente se todos os outros saírem da reunião**                 | Habilitado<br>Desabilitado                                              | Sim                |
| **Ingressar em reuniões de terceiros**                 | Cisco Webex<br>Zoom                                              | Sim                |
| **Ingressar com informações de sala**                 | Selecionado<br>Desmarcado                                              | Sim                |
| **Ingressar com informações personalizadas**                 | Selecionado<br>Desmarcado                                              | Sim                |
| **Nome (obrigatório)**                 | Nome da sala ou espaço                                              | Sim                |
| **Email (obrigatório)**                 | Endereço de email                                              | Sim                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modo de monitor duplo**                                        | Habilitado<br>Desabilitado                                              | Sim                |
| **Permitir duplicação de conteúdo** | Selecionado<br>Desmarcado                                 | Sim                |
| **Bluetooth sinalizador**                                      | Habilitado<br>Desabilitado                                              | Sim                |
| **Aceitar automaticamente convites de reunião baseados em proximidade** | Selecionado<br>Desmarcado                                 | Sim                |
| **Enviar logs com comentários**                                  | Habilitado<br>Desabilitado                                              | Sim                |
| **Endereço de email para logs e comentários**                      | Endereço de email                                          | Sim                |
| *Coordenar reuniões*                                                     |                                                        |                    |
| **Reuniões Coordenadas** | Habilitado<br>Desabilitado                                 | Não                |
| **Ativar o microfone deste dispositivo** | Habilitado<br>Desabilitado                                 | Não                |
| **Permitir que as pessoas habilitem ao ingressar em uma reunião** | Selecionado<br>Desmarcado                                 | Não                |
| **Ativar a câmera deste dispositivo** | Habilitado<br>Desabilitado                                 | Não                |
| **Permitir que as pessoas habilitem ao ingressar em uma reunião** | Selecionado<br>Desmarcado                                 | Não                |
| **Ativar o quadro de comunicações para este dispositivo** | Habilitado<br>Desabilitado                                 | Não                |
| **Contas de dispositivo confiáveis (separadas por vírgulas)** | Lista de dispositivos                              | Não                |
| *Periféricos*                                                |                                                        |                    |
| **Microfone de conferência**                                  | Lista de microfones disponíveis                          | Não                 |
| **Palestrante de conferência**                                     | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Alto-falante padrão**                                          | Lista de alto-falantes disponíveis                             | Não                 |
| **Volume padrão**                                           | 0-100                                                  | Não                 |
| **Câmera de conteúdo**                                           | Lista de câmeras disponíveis                              | Não                 |
| **Aprimoramentos da câmera de conteúdo**                              | Habilitado<br>Desabilitado                                              | Não                 |
| **Girar a Câmera de Conteúdo 180 graus**                        | Habilitado<br>Desabilitado                                              | Não                 |
| *Temas*                                                    |                                                        |                    |
|                                                              | Padrão<br>Nenhum tema<br>Personalizado<br>Lista de temas internos   | Sim                |

### <a name="cortana-settings"></a>Cortana configurações

Você pode habilitar _Cortana ativação_ de voz ou _push_ para conversar usando o PowerShell para todos os dispositivos em sua organização ou para cada dispositivo separadamente.

Consulte [Salas do Microsoft Teams no Windows](../cortana-in-teams.md) no artigo "Cortana de voz no Teams".

### <a name="front-row-layout-settings"></a>Configurações de layout da linha da frente

A linha frontal é a opção de layout do modo de exibição de reunião Salas do Teams no Windows.

| Teams dispositivo | Versão do aplicativo | Exibição frontal da sala |
|--------------|-------------|-----------------------|
|Salas do Microsoft Teams no Windows | 4.11.12.0 ou superior (a versão mais recente é recomendada) | Dá suporte a telas simples e duplas; Tamanho mínimo: 46 polegadas; Taxa de proporção 16:9 com resolução 1920x1080 ou 21:9 com resolução 2560x1080; Todas as exibições devem ser definidas em 100% de dimensionamento em Windows configurações |

Consulte [Salas do Microsoft Teams manutenção e operações](rooms-operations.md#scale-and-resolution) para ajustar as configurações de exibição para atender aos requisitos da linha da frente.

Para saber como definir a linha de frente como o layout padrão de uma sala ou como desativá-la, consulte Gerenciar um console Salas do Microsoft Teams configurações [remotamente](xml-config-file.md#set-front-row-as-the-default-layout) com um arquivo de configuração XML.

Consulte [Problemas conhecidos para](known-issues.md#Limits) obter mais informações sobre como gerenciar a linha de frente.

## <a name="device-restart-options"></a>Opções de reinicialização do dispositivo

As alterações nas configurações do dispositivo só entrarão em vigor depois que Salas do Teams tiver sido reiniciado. Ao fazer alterações que precisam de uma reinicialização, você pode optar por reiniciar imediatamente ou agendar uma reinicialização. Aqui estão as opções de reinicialização disponíveis:

- **Reinicialização imediata** Se você escolher essa opção, todos os dispositivos nos quais você está fazendo alterações serão reiniciados assim que você selecionar essa opção.
- **Reinicialização agendada** Se você escolher essa opção, poderá reiniciar os dispositivos nos quais está fazendo alterações em um momento que seja menos prejudicial para sua organização.
  - **Selecionar data e hora** – escolha a data e a hora específicas para reiniciar o dispositivo. A data e a hora escolhidas são locais para o dispositivo que está sendo reiniciado. 
  - **Deixar a atualização para reinicialização noturna** Os dispositivos são reiniciados à noite para executar a manutenção. As alterações feitas nos dispositivos serão aplicadas durante essa reinicialização.

> [!CAUTION]
> Salas do Teams que estão em uso no momento de uma reinicialização ficará indisponível durante o processo de reinicialização. Eles serão desconectados de reuniões em andamento e não estarão disponíveis para ingressar em novas reuniões.

## <a name="remove-device"></a>Remover dispositivo

Quando você remove um dispositivo, o dispositivo é removido da sua organização e não aparece mais na lista de Salas do Teams no Windows no centro de administração do Teams.

Se você remover um dispositivo e ele ainda estiver configurado com um nome de usuário e uma senha válidos, ele será adicionado automaticamente à sua lista do Salas do Teams se ele se conectar ao Microsoft 365 novamente.

Para remover um ou mais dispositivos, faça o seguinte:

1. Vá para **Teams Dispositivos** >  **Salas do Teams no Windows** e selecione os dispositivos que você deseja remover.
2. Selecione **Remover**.

## <a name="download-device-logs"></a>Baixar logs de dispositivo

Você pode baixar uma cópia dos arquivos de log de diagnóstico de um dispositivo, se solicitado pelo suporte da Microsoft. Os arquivos de log são compactados em um arquivo zip que pode ser baixado do Teams de administração.

Para baixar logs de um Salas do Teams para o computador, faça o seguinte:

1. Vá para **Teams Dispositivos** >  **Salas do Teams no Windows** e selecione o nome do dispositivo do qual você deseja baixar os logs.
1. Selecione **Baixar logs do dispositivo**. Pode levar vários minutos para que os logs do dispositivo se tornem disponíveis.
1. Selecione a **guia Histórico** e, em seguida, selecione o link do arquivo de log **no arquivo de diagnóstico**. Um arquivo zip que contém os arquivos de log de diagnóstico do dispositivo será baixado para a pasta Downloads padrão do navegador.

## <a name="view-device-information"></a>Exibir informações do dispositivo

No centro Teams de administração, você pode exibir o status geral de todos os dispositivos em sua organização e exibir detalhes de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Salas do Teams do sistema

O Salas do Teams do sistema mostra rapidamente o status e a integridade de todos os seus dispositivos.

### <a name="device-details-view"></a>Exibição de detalhes do dispositivo

Para exibir informações detalhadas sobre um dispositivo, selecione seu nome na lista de dispositivos. Quando estiver na exibição de detalhes, você poderá ver as seguintes informações sobre seu dispositivo:

- **Status de integridade** Mostra a integridade geral do dispositivo Teams Room. O status de integridade pode ser **íntegro** **ou não íntegro**.
- **Offline desde** Mostra a última vez Microsoft 365 foi capaz de se comunicar com o dispositivo.
- **Status do dispositivo** Mostra o estado atual do dispositivo: **Ocioso**, **Teams reunião**, Skype **reunião** ou **Ingestão**.
- **Periféricos** Mostra os periféricos conectados ao seu dispositivo Teams Room e seu status de integridade. O status de integridade pode **ser Conectado** ou **Desconectado**.
- **Saúde** Mostra informações detalhadas sobre os periféricos conectados ao seu dispositivo de sala Teams, conectividade de rede, status de entrada para os serviços necessários e informações de versão do software.
- **Detalhes** Mostra as informações do fabricante, o endereço IP de rede e Teams endereço SERIAL/MAC do dispositivo de sala.
- **Atividade** Mostra detalhes da reunião anterior, incluindo a data e a hora da reunião, o número de participantes, a duração e a qualidade do áudio. Para obter mais informações sobre detalhes da reunião, consulte a seção [Detalhes da atividade da](#meeting-activity-details) reunião mais adiante neste artigo.
- **História** Mostra um histórico da atividade de gerenciamento no dispositivo Teams Room, incluindo atualizações de configuração, reinicializações do dispositivo e links de download de log do dispositivo.

#### <a name="meeting-activity-details"></a>Detalhes da atividade da reunião

A **guia** Atividade em Teams detalhes do dispositivo de sala mostra informações detalhadas e de alto nível sobre todas as reuniões das quais o dispositivo participou ao longo do tempo. Na guia **Atividade** , você pode ver quando uma reunião foi realizada, quantos participantes participaram da reunião e a qualidade do áudio durante a reunião.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams resumo da atividade do dispositivo de sala.":::

Para ver as informações detalhadas sobre uma reunião específica, selecione a data e a hora da reunião sobre a qual você deseja obter mais informações. Se uma reunião tiver apenas dois participantes, você verá a página de detalhes do participante; caso contrário, você verá uma página de resumo do participante.

##### <a name="participant-summary"></a>Resumo do participante

A página de resumo do participante mostra todos os participantes que participaram da reunião. Você pode ver quando cada participante ingressou na reunião, seu nome, qualidade de áudio e quais recursos foram usados durante a sessão. Para exibir os detalhes da sessão de um participante, selecione a hora de início da sessão para esse participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams de conferência do dispositivo de sala.":::

##### <a name="participant-details"></a>Detalhes do participante

A página de detalhes do participante mostra informações de diagnóstico de ponta a ponta para a sessão desse participante. Conforme mostrado no gráfico a **seguir, as** informações de  **dispositivo, sistema** e conectividade são fornecidas para o participante e para o Salas do Teams dispositivo. **As** informações de diagnóstico de rede entre o participante e o Salas do Teams dispositivo também são fornecidas. Selecione o ícone do contexto sobre o qual você deseja obter mais informações. Para obter informações de diagnóstico adicionais, selecione **a guia** Avançado.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams detalhes da chamada do dispositivo de sala.":::
