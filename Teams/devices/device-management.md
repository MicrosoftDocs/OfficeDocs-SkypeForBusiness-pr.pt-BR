---
title: Gerenciar seus dispositivos no Microsoft Teams
author: dstrome
ms.author: dstrome
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
description: Saiba como gerenciar dispositivos usados com o Teams em sua organização.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41213955c9e57829208ce0ec98448195dc266044
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50350588"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gerenciar seus dispositivos no Microsoft Teams

Você pode gerenciar dispositivos usados com o Microsoft Teams em sua organização a partir do centro de administração do Microsoft Teams. Você pode exibir e gerenciar o inventário de dispositivos para sua organização e realizar tarefas como atualizar, reiniciar e monitorar diagnósticos para dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.

Para gerenciar dispositivos, como alterar a configuração do dispositivo, reiniciar dispositivos, gerenciar atualizações ou exibir a saúde do dispositivo e periféricos, você precisa receber uma das seguintes funções de administrador do Microsoft 365:

- Administrador global do Microsoft 365
- Administrador do Serviço do Teams
- Administrador de dispositivos do Teams

Para obter mais informações sobre funções de administrador no Teams, [consulte Use Teams administrator roles to manage Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?

Você pode gerenciar qualquer dispositivo certificado e inscrito no Teams. Um dispositivo é automaticamente inscrito na primeira vez que um usuário se inscreva no Teams no dispositivo. Para uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Barras de colaboração](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Salas do Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Exibições do Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Painéis do Teams](teams-panels.md)

Para gerenciar dispositivos, na navegação à esquerda do centro de administração do [Microsoft Teams,](https://admin.teams.microsoft.com)vá para **Dispositivos** e selecione o tipo de dispositivo. Cada tipo de dispositivo tem sua própria seção respectiva, que permite gerenciá-los separadamente.

## <a name="manage-teams-rooms-devices"></a>Gerenciar dispositivos teams rooms

Você pode usar o Centro de administração do Teams para exibir e gerenciar remotamente seus dispositivos salas do Teams em toda a sua organização. O Centro de administração do Teams facilita a visão, rapidamente, de quais dispositivos são saudáveis e que precisam de atenção e permite que você se concentre em dispositivos específicos para ver informações detalhadas sobre a saúde do dispositivo, o desempenho da reunião, a qualidade da chamada e os periféricos. 

Aqui estão algumas coisas que você pode fazer para gerenciar seus dispositivos salas do Teams. Os dispositivos teams Rooms podem ser encontrados no centro de [administração do Microsoft Teams](https://admin.teams.microsoft.com) em Salas **do** Teams de  >  **Dispositivos.**

Para obter detalhes sobre como gerenciar seus dispositivos de Salas do Teams, consulte [Manage Microsoft Teams Rooms](../rooms/rooms-manage.md).

| Para fazer isso...                          | Faça isto                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar configurações em um ou mais dispositivos | Selecione um ou mais dispositivos > **Configurações de Edição.** Se você selecionar vários dispositivos, os valores que você alterar substituirão os valores em todos os dispositivos selecionados.                                                                                                                                                                                                                       |
| Reiniciar dispositivos                        | Selecione um ou mais dispositivos > **Reiniciar**. Ao reiniciar um dispositivo, você pode optar por  reiniciar o dispositivo imediatamente ou selecionar Agendar a reinicialização para reiniciar o dispositivo em uma data e hora específicas. A data e a hora selecionadas são locais para o dispositivo que está sendo reiniciado.                                                                                            |
| Exibir atividade de reunião                  | Selecione um nome de dispositivo para abrir detalhes do dispositivo > **Atividade**. Ao abrir a guia **Atividade,** você pode ver todas as reuniões nas que o dispositivo participou. Este modo de exibição de resumo mostra a hora de início da reunião, o número de participantes, sua duração e a qualidade geral da chamada.                                                                                        |
| Exibir detalhes da reunião                   | Selecione um nome de dispositivo para abrir os detalhes do dispositivo > **Atividade** > selecionar uma reunião. Quando você abre os detalhes de uma reunião, você pode ver todos os participantes da reunião, quanto tempo eles estavam na chamada, os tipos de sessão do Teams e sua qualidade de chamada individual. Se você quiser ver informações técnicas sobre a chamada de um participante, selecione a hora de início da chamada do participante. |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>Gerenciar telefones, barras de colaboração, exibições do Teams e painéis do Teams 

No Centro de administração do Teams, você pode exibir e gerenciar telefones, barras de colaboração, exibições do Teams e painéis do Teams inscritos no Teams em sua organização. As informações que você verá para cada dispositivo incluem nome do dispositivo, fabricante, modelo, usuário, status, ação, última vez vista e histórico. Você pode personalizar a exibição para mostrar as informações que se ajustam às suas necessidades.

Telefones, barras de colaboração, exibições do Teams e painéis do Teams são automaticamente inscritos no Microsoft Intune se você se inscreveu. Depois que um dispositivo é inscrito, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

Aqui estão alguns exemplos de como você pode gerenciar telefones, barras de colaboração, exibições do Teams e painéis do Teams em sua organização.  

| Para fazer isso...                           | Faça isto                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar informações do dispositivo               | Selecione um dispositivo > **Editar**. Você pode editar detalhes como nome do dispositivo, marca de ativo e adicionar anotações.                                                                                                                                                                                                              |
| Gerenciar atualizações de software                 | Selecione um dispositivo > **Update**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a instalar. Para obter mais informações sobre a atualização de dispositivos, consulte [Atualizar dispositivos do Teams remotamente](remote-update.md)                                                          |
| Atualizar telefones do Teams para exibições do Teams  | Na página **Telefones IP,** selecione um ou mais telefones do Teams > **Upgrade**. Essa opção está disponível apenas para telefones que suportam a atualização para exibições do Teams. Para saber mais, confira [Upgrade Teams phones to Teams displays](upgrade-phones-to-displays.md).                                                      |
| Atribuir ou alterar políticas de configuração | Selecione um ou mais dispositivos > **Atribuir configuração**.                                                                                                                                                                                                                                                       |
| Adicionar ou remover marcas de dispositivo               | Selecione um ou mais dispositivos > **Gerenciar marcas**. Para obter mais informações sobre marcas de dispositivo, consulte [Manage Teams device tags](manage-device-tags.md).                                                                                                                                                                 |
| Reiniciar dispositivos                         | Selecione um ou mais dispositivos > **Reiniciar**.                                                                                                                                                                                                                                                                    |
| Filtrar dispositivos usando marcas de dispositivo        | Selecione o ícone de filtro, selecione o campo **Marca,** especifique uma marca de dispositivo para filtrar e selecione **Aplicar**. Para obter mais informações sobre a filtragem de dispositivos usando marcas de dispositivo, [consulte Use filters to return devices with a specific tag](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Exibir histórico e diagnóstico do dispositivo     | Na coluna **Histórico,** clique no link **Exibir** para um dispositivo para exibir seu histórico de atualizações e detalhes diagóticos.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar configurações e recursos para diferentes dispositivos do Teams em sua organização, incluindo barras de colaboração, exibições do Teams, telefone do Teams e painéis do Teams. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou conjunto de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

Para criar um perfil de configuração para um tipo de dispositivo do Teams:

1. Na navegação à esquerda, vá para **Dispositivos** > selecione o tipo de dispositivo do Teams > **perfis de configuração.** Por exemplo, selecione  >  **Painéis do Teams Dispositivos**  >  **Perfis** de configuração para criar um novo perfil de configuração para painéis do Teams.
2. Clique em **Adicionar**.
3. Insira um nome para o perfil e, opcionalmente, adicione uma descrição amigável.
4. Especifique as configurações que você deseja para o perfil e clique em **Salvar**.
   O perfil de configuração recém-criado é exibido na lista de perfis.

#### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração
Depois de criar um perfil de configuração para um tipo de dispositivo do Teams, atribua-o a um ou mais dispositivos.

1. Na navegação à esquerda, vá para **Dispositivos** > selecione o tipo de dispositivo do Teams. Por exemplo, para atribuir um perfil de configuração a um dispositivo de painéis do Teams, selecione   >  **Dispositivos Painéis do Teams**.
2. Selecione um ou mais dispositivos e clique em **Atribuir configuração**.  
3. No painel **Atribuir um painel de** configuração, pesquise o perfil de configuração a ser atribuído aos dispositivos selecionados.
4. Clique em **Aplicar**.
   Para os dispositivos aos quais você aplicou a política de configuração, a coluna **Ação** exibe **Config Update** e a coluna **Perfil** de Configuração exibe o nome do perfil de configuração.
