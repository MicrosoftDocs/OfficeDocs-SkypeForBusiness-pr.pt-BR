---
title: Gerenciar seus dispositivos no Microsoft Teams
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Saiba como gerenciar dispositivos usados com Teams em sua organização.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4346d82e490d28840e029d257cbeeb4c4e10765
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "65220252"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams: gerenciando seus dispositivos 

Você pode gerenciar dispositivos usados com Microsoft Teams em sua organização no Microsoft Teams de administração. Você pode exibir e gerenciar o inventário de dispositivos para sua organização e realizar tarefas como atualizar, reiniciar e monitorar o diagnóstico de dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.

Para gerenciar dispositivos, como alterar a configuração do dispositivo, reiniciar dispositivos, gerenciar atualizações ou exibir a integridade do dispositivo e periférico, você precisa receber uma das seguintes funções de administrador Microsoft 365:

- Microsoft 365 Administrador global
- Teams de serviço
- Teams administrador do dispositivo

Para obter mais informações sobre funções de administrador no Teams, consulte [Usar funções Teams administrador para gerenciar Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?

Você pode gerenciar qualquer dispositivo certificado e registrado no Teams. Um dispositivo é registrado automaticamente na primeira vez que um usuário entra Teams no dispositivo. Para obter uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Salas do Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams exibições](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams painéis](teams-panels.md)

Para gerenciar dispositivos, na navegação à esquerda do centro [de](https://admin.teams.microsoft.com) administração Microsoft Teams, acesse **Teams Dispositivos** e selecione o tipo de dispositivo. Cada tipo de dispositivo tem sua própria seção respectiva, que permite gerenciá-los separadamente.

## <a name="manage-teams-rooms-on-windows-devices"></a>Gerenciar Salas do Teams em Windows dispositivos

Você pode usar o Teams de administração para exibir e gerenciar remotamente seu Salas do Teams em Windows em toda a organização. O centro de administração do Teams torna mais fácil ver, rapidamente, quais dispositivos estão íntegros e que precisam de atenção e permite que você se concentre em dispositivos específicos para ver informações detalhadas sobre integridade do dispositivo, desempenho de reunião, qualidade de chamadas e periféricos. 

Aqui estão algumas coisas que você pode fazer para gerenciar seus Salas do Teams dispositivos. Salas do Teams dispositivos podem ser encontrados [no centro de administração Microsoft Teams em](https://admin.teams.microsoft.com) **Teams Dispositivos** >  **Salas do Teams no Windows**.

Para obter detalhes sobre como gerenciar seus dispositivos Salas do Teams, consulte [Gerenciar Salas do Microsoft Teams](../rooms/rooms-manage.md).

| Para fazer isso...                          | Faça isso                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar configurações em um ou mais dispositivos | Selecione um ou mais dispositivos > **editar configurações**. Se você selecionar vários dispositivos, os valores alterados substituirão os valores em todos os dispositivos selecionados.                                                                                                                                                                                                                       |
| Reiniciar dispositivos                        | Selecione um ou mais dispositivos > **Reiniciar**. Ao reiniciar um dispositivo, você pode optar por reiniciar o dispositivo imediatamente ou selecionar Agendar  reinicialização para reiniciar o dispositivo em uma data e hora específicas. A data e a hora selecionadas são locais para o dispositivo que está sendo reiniciado.                                                                                            |
| Exibir atividade de reunião                  | Selecione um nome de dispositivo para abrir os detalhes do dispositivo > **Atividade**. Ao abrir a **guia Atividade** , você pode ver todas as reuniões das que o dispositivo participou. Esta exibição de resumo mostra a hora de início da reunião, o número de participantes, sua duração e a qualidade geral da chamada.                                                                                        |
| Exibir detalhes da reunião                   | Selecione um nome de dispositivo para abrir os detalhes do dispositivo > **atividade >** selecionar uma reunião. Ao abrir os detalhes de uma reunião, você pode ver todos os participantes da reunião, por quanto tempo eles estavam na chamada, os tipos de sessão Teams e sua qualidade de chamada individual. Se você quiser ver informações técnicas sobre a chamada de um participante, selecione a hora de início da chamada do participante. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Gerenciar telefones, Salas do Teams no Android, Teams telas e Teams painéis 

No centro de administração do Teams, você pode exibir e gerenciar telefones, Salas do Teams no Android, exibições do Teams e painéis Teams registrados no Teams em sua organização. As informações que você verá para cada dispositivo incluem nome do dispositivo, fabricante, modelo, usuário, status, ação, visto pela última vez e histórico. Você pode personalizar a exibição para mostrar as informações que atendem às suas necessidades.

Telefones, Salas do Teams no Android, Teams telas e painéis Teams são registrados automaticamente no Microsoft Intune se você tiver se inscrito nele. Depois que um dispositivo é registrado, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

Aqui estão alguns exemplos de como você pode gerenciar telefones, Salas do Teams no Android, Teams e painéis Teams em sua organização.  

| Para fazer isso...                           | Faça isso                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar informações do dispositivo               | Selecione um dispositivo > **Editar**. Você pode editar detalhes, como nome do dispositivo, marca de ativo e adicionar anotações.                                                                                                                                                                                                              |
| Gerenciar atualizações de software                 | Selecione um dispositivo > **Atualização**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a serem instaladas. Para obter mais informações sobre como atualizar dispositivos, consulte [Atualizar Teams dispositivos remotamente](remote-update.md)                                                          |
| Atualizar Teams para Teams telas  | Na página **telefones IP**, selecione um ou mais Teams telefone > **Atualização**. Essa opção está disponível somente para telefones que dão suporte à atualização para Teams telas. Para saber mais, confira [Atualizar Teams para Teams telas](upgrade-phones-to-displays.md).                                                      |
| Atribuir ou alterar políticas de configuração | Selecione um ou mais dispositivos para > **a configuração**.                                                                                                                                                                                                                                                       |
| Adicionar ou remover marcas de dispositivo               | Selecione um ou mais dispositivos para > **Gerenciar marcas**. Para obter mais informações sobre marcas de dispositivo, [consulte Gerenciar Teams de dispositivo](manage-device-tags.md).                                                                                                                                                                 |
| Reiniciar dispositivos                         | Selecione um ou mais dispositivos > **Reiniciar**.                                                                                                                                                                                                                                                                    |
| Filtrar dispositivos usando marcas de dispositivo        | Selecione o ícone de filtro, selecione o **campo Marca** , especifique uma marca de dispositivo para filtrar e selecione **Aplicar**. Para obter mais informações sobre como filtrar dispositivos usando marcas de dispositivo, [consulte Usar filtros para retornar dispositivos com uma marca específica](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Exibir histórico e diagnóstico do dispositivo     | Na coluna **Histórico** , clique no link **Exibir** de um dispositivo para exibir seu histórico de atualizações e detalhes de diagnóstico.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar configurações e recursos para diferentes dispositivos Teams em sua organização, incluindo Salas do Teams no Android, telas do Teams, telefone Teams e painéis Teams. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que deseja habilitar ou desabilitar e, em seguida, atribuir um perfil a um dispositivo ou conjunto de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

Para criar um perfil de configuração para um Teams tipo de dispositivo:

1. No painel de navegação esquerdo, vá para **Teams dispositivos** > o tipo de dispositivo Teams os perfis de **configuração do >.** Por exemplo, selecione **Teams dispositivos** >  **Teams panelsConfiguration** >  para criar um novo perfil de configuração para Teams painéis.
2. Clique em **Adicionar**.
3. Insira um nome para o perfil e, opcionalmente, adicione uma descrição amigável.
4. Especifique as configurações desejadas para o perfil e clique em **Salvar**.
   O perfil de configuração recém-criado é exibido na lista de perfis.

#### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração
Depois de criar um perfil de configuração para Teams tipo de dispositivo, atribua-o a um ou mais dispositivos.

1. No painel de navegação esquerdo, vá para **Teams dispositivos >** selecione o tipo Teams dispositivo. Por exemplo, para atribuir um perfil de configuração a um dispositivo Teams painéis, selecione Teams **dispositivos** >  **Teams painéis**.
2. Selecione um ou mais dispositivos e clique em **Atribuir configuração**.  
3. No painel **Atribuir uma configuração** , pesquise o perfil de configuração a ser atribuído aos dispositivos selecionados.
4. Clique em **Aplicar**.
   Para os **dispositivos aos** quais você aplicou a política de configuração, a coluna Ação exibe a Atualização de  Configuração e a coluna Perfil de configuração exibe o nome do perfil de configuração.
