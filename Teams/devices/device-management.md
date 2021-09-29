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
description: Saiba como gerenciar dispositivos usados com Teams em sua organização.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2baa4755f63bbb5867a1e259c9edc9a3aeca0718
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59993166"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gerenciar seus dispositivos no Microsoft Teams

Você pode gerenciar dispositivos usados com Microsoft Teams em sua organização a partir do Microsoft Teams de administração. Você pode exibir e gerenciar o inventário de dispositivos para sua organização e realizar tarefas como atualizar, reiniciar e monitorar diagnósticos para dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.

Para gerenciar dispositivos, como alterar a configuração do dispositivo, reiniciar dispositivos, gerenciar atualizações ou exibir a saúde do dispositivo e periféricos, você precisa receber uma das seguintes funções de administrador Microsoft 365:

- Microsoft 365 Administrador global
- Teams Administrador do serviço
- Teams Administrador de dispositivo

Para obter mais informações sobre funções de administrador Teams, consulte Use Teams de administrador [para gerenciar Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?

Você pode gerenciar qualquer dispositivo certificado e inscrito Teams. Um dispositivo é automaticamente inscrito na primeira vez que um usuário faz logo Teams no dispositivo. Para uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Barras de colaboração](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Salas do Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams exibe](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams painéis](teams-panels.md)

Para gerenciar dispositivos, na navegação à esquerda do centro de administração [Microsoft Teams,](https://admin.teams.microsoft.com)vá para Teams **Dispositivos** e selecione o tipo de dispositivo. Cada tipo de dispositivo tem sua própria seção respectiva, que permite gerenciá-los separadamente.

## <a name="manage-teams-rooms-devices"></a>Gerenciar Salas do Teams dispositivos

Você pode usar o Teams de administração para exibir e gerenciar remotamente seus Salas do Teams em toda a sua organização. O Teams de administração torna mais fácil ver, rapidamente, quais dispositivos são saudáveis e que precisam de atenção e permite que você se concentre em dispositivos específicos para ver informações detalhadas sobre a saúde do dispositivo, desempenho da reunião, qualidade de chamada e periféricos. 

Aqui estão algumas coisas que você pode fazer para gerenciar seus Salas do Teams dispositivos. Salas do Teams dispositivos podem ser encontrados no centro de administração [Microsoft Teams em](https://admin.teams.microsoft.com) **Teams Devices**  >  **Salas do Teams**.

Para obter detalhes sobre como gerenciar seus dispositivos Salas do Teams, consulte [Manage Salas do Microsoft Teams](../rooms/rooms-manage.md).

| Para fazer isso...                          | Faça isso                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar configurações em um ou mais dispositivos | Selecione um ou mais dispositivos > **Configurações de Edição.** Se você selecionar vários dispositivos, os valores que você alterar substituirão os valores em todos os dispositivos selecionados.                                                                                                                                                                                                                       |
| Reiniciar dispositivos                        | Selecione um ou mais dispositivos > **Reiniciar**. Ao reiniciar um dispositivo, você pode optar por  reiniciar o dispositivo imediatamente ou selecionar Agendar a reinicialização para reiniciar o dispositivo em uma data e hora específicas. A data e a hora selecionadas são locais para o dispositivo que está sendo reiniciado.                                                                                            |
| Exibir atividade de reunião                  | Selecione um nome de dispositivo para abrir detalhes do dispositivo > **Atividade**. Ao abrir a guia **Atividade,** você pode ver todas as reuniões nas que o dispositivo participou. Este modo de exibição de resumo mostra a hora de início da reunião, o número de participantes, sua duração e a qualidade geral da chamada.                                                                                        |
| Exibir detalhes da reunião                   | Selecione um nome de dispositivo para abrir os detalhes do dispositivo > **Atividade** > selecionar uma reunião. Quando você abre os detalhes de uma reunião, você pode ver todos os participantes da reunião, quanto tempo eles estavam na chamada, os tipos de sessão Teams e sua qualidade de chamada individual. Se você quiser ver informações técnicas sobre a chamada de um participante, selecione a hora de início da chamada do participante. |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>Gerenciar telefones, barras de colaboração, Teams exibições e Teams painéis 

No Teams de administração, você pode exibir e gerenciar telefones, barras de colaboração, Teams exibições e Teams painéis inscritos no Teams em sua organização. As informações que você verá para cada dispositivo incluem nome do dispositivo, fabricante, modelo, usuário, status, ação, última vez vista e histórico. Você pode personalizar a exibição para mostrar as informações que se ajustam às suas necessidades.

Telefones, barras de colaboração, Teams e painéis Teams são automaticamente inscritos no Microsoft Intune se você se inscreveu. Depois que um dispositivo é inscrito, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

Aqui estão alguns exemplos de como você pode gerenciar telefones, barras de colaboração, Teams exibições e Teams painéis em sua organização.  

| Para fazer isso...                           | Faça isso                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar informações do dispositivo               | Selecione um dispositivo > **Editar**. Você pode editar detalhes como nome do dispositivo, marca de ativo e adicionar anotações.                                                                                                                                                                                                              |
| Gerenciar atualizações de software                 | Selecione um dispositivo > **Update**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a instalar. Para obter mais informações sobre a atualização de dispositivos, consulte [Atualizar Teams dispositivos remotamente](remote-update.md)                                                          |
| Atualizar Teams telefones para Teams displays  | Na página **Telefones IP,** selecione um ou mais telefones Teams > **Upgrade**. Essa opção está disponível somente para telefones que suportam a atualização para Teams displays. Para saber mais, consulte [Upgrade Teams phones to Teams displays](upgrade-phones-to-displays.md).                                                      |
| Atribuir ou alterar políticas de configuração | Selecione um ou mais dispositivos > **Atribuir configuração**.                                                                                                                                                                                                                                                       |
| Adicionar ou remover marcas de dispositivo               | Selecione um ou mais dispositivos > **Gerenciar marcas**. Para obter mais informações sobre marcas de dispositivo, consulte [Manage Teams device tags](manage-device-tags.md).                                                                                                                                                                 |
| Reiniciar dispositivos                         | Selecione um ou mais dispositivos > **Reiniciar**.                                                                                                                                                                                                                                                                    |
| Filtrar dispositivos usando marcas de dispositivo        | Selecione o ícone de filtro, selecione o campo **Marca,** especifique uma marca de dispositivo para filtrar e selecione **Aplicar**. Para obter mais informações sobre a filtragem de dispositivos usando marcas de dispositivo, [consulte Use filters to return devices with a specific tag](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Exibir histórico e diagnóstico do dispositivo     | Na coluna **Histórico,** clique no link **Exibir** para um dispositivo para exibir seu histórico de atualizações e detalhes de diagnóstico.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração em Teams

Use perfis de configuração para gerenciar configurações e recursos para diferentes dispositivos Teams em sua organização, incluindo barras de colaboração, Teams displays, telefone Teams e painéis Teams de segurança. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou conjunto de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

Para criar um perfil de configuração para um Teams tipo de dispositivo:

1. Na navegação à esquerda, vá para Teams **Dispositivos** > selecione o tipo Teams de dispositivo > **perfis de configuração**. Por exemplo, selecione **Teams**  >  **Dispositivos Teams painéis Perfis** de configuração para criar um novo perfil de configuração para Teams  >   painéis.
2. Clique em **Adicionar**.
3. Insira um nome para o perfil e, opcionalmente, adicione uma descrição amigável.
4. Especifique as configurações que você deseja para o perfil e clique em **Salvar**.
   O perfil de configuração recém-criado é exibido na lista de perfis.

#### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração
Depois de criar um perfil de configuração para um Teams de dispositivo, atribua-o a um ou mais dispositivos.

1. Na navegação à esquerda, vá para Teams **Dispositivos** > selecione o tipo Teams dispositivo. Por exemplo, para atribuir um perfil de configuração a um Teams de painéis, selecione **Teams**  >  **Dispositivos Teams painéis**.
2. Selecione um ou mais dispositivos e clique em **Atribuir configuração**.  
3. No painel **Atribuir um painel de** configuração, pesquise o perfil de configuração a ser atribuído aos dispositivos selecionados.
4. Clique em **Aplicar**.
   Para os dispositivos aos quais você aplicou a política de configuração, a coluna **Ação** exibe **Config Update** e a coluna **Perfil** de Configuração exibe o nome do perfil de configuração.
