---
title: Gerenciar dispositivos no Microsoft Teams
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
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Gerenciar dispositivos usados com o Microsoft Teams em sua organização.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e545a6d4208e6f54abbf72327cf887d45b34e141
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2023
ms.locfileid: "69807438"
---
# <a name="manage-devices-in-teams"></a>Gerenciar dispositivos no Teams 

Você pode gerenciar dispositivos usados com o Microsoft Teams em sua organização no centro de administração do Microsoft Teams. Você pode exibir e gerenciar o inventário de dispositivos para sua organização e fazer tarefas como atualizar, reiniciar e monitorar o diagnóstico de dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.

Para gerenciar dispositivos, como alterar a configuração do dispositivo, reiniciar dispositivos, gerenciar atualizações ou exibir o dispositivo e a integridade periférica, você precisa receber uma das seguintes funções de administrador do Microsoft 365:

- Administrador global do Microsoft 365
- Administrador do Serviço do Teams
- Administrador do Dispositivo do Teams

Para obter mais informações sobre funções de administrador no Teams, consulte [Usar funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?

Você pode gerenciar qualquer dispositivo certificado e registrado no Teams. Um dispositivo é registrado automaticamente na primeira vez que um usuário entra no Teams no dispositivo. Para obter uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Salas do Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Exibições do Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Painéis do Teams](teams-panels.md)

Para gerenciar dispositivos, na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com), acesse **Dispositivos do Teams** e selecione o tipo de dispositivo. Cada tipo de dispositivo tem sua própria seção, o que permite gerenciá-los separadamente.

## <a name="manage-teams-rooms-on-windows-devices"></a>Gerenciar Salas do Teams em dispositivos Windows

Você pode usar o centro de administração do Teams para exibir e gerenciar remotamente sua Salas do Teams em dispositivos Windows em toda a sua organização. O centro de administração do Teams facilita a visualização, rapidamente, de quais dispositivos são saudáveis e que precisam de atenção e permite que você se concentre em dispositivos específicos para ver informações detalhadas sobre integridade do dispositivo, desempenho da reunião, qualidade de chamada e periféricos. 

Aqui estão algumas coisas que você pode fazer para gerenciar seus dispositivos Salas do Teams. Salas do Teams dispositivos podem ser encontrados no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) em **Dispositivos** >  do Teams **Salas do Teams no Windows**.

Para obter detalhes sobre como gerenciar seus dispositivos Salas do Teams, consulte [Gerenciar Salas do Microsoft Teams](../rooms/rooms-manage.md).

| Para fazer isso...                          | Faça isso                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar configurações em um ou mais dispositivos | Selecione um ou mais dispositivos > **Editar configurações**. Se você selecionar vários dispositivos, os valores alterados substituirão os valores em todos os dispositivos selecionados.                                                                                                                                                                                                                       |
| Reiniciar dispositivos                        | Selecione um ou mais dispositivos > **Reiniciar**. Ao reiniciar um dispositivo, você pode escolher se deve reiniciar o dispositivo imediatamente ou selecionar **Agendar a reinicialização** para reiniciar o dispositivo em uma data e hora específicas. A data e a hora selecionadas são locais para o dispositivo que está sendo reiniciado.                                                                                            |
| Exibir atividade de reunião                  | Selecione um nome de dispositivo para abrir detalhes do dispositivo > **Atividade**. Ao abrir a guia **Atividade** , você pode ver todas as reuniões nas quais o dispositivo participou. Esta exibição de resumo mostra a hora de início da reunião, o número de participantes, sua duração e a qualidade geral da chamada.                                                                                        |
| Exibir detalhes da reunião                   | Selecione um nome de dispositivo para abrir detalhes do dispositivo > **Atividade** > selecionar uma reunião. Quando você abre os detalhes de uma reunião, você pode ver todos os participantes da reunião, quanto tempo eles estavam na chamada, os tipos de sessão do Teams e sua qualidade de chamada individual. Se você quiser ver informações técnicas sobre a chamada de um participante, selecione a hora de início da chamada do participante. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Gerenciar telefones, Salas do Teams em painéis Android, Teams e Teams 

No centro de administração do Teams, você pode exibir e gerenciar telefones, Salas do Teams nos painéis Android, Teams e Teams registrados no Teams em sua organização. As informações que você verá para cada dispositivo incluem nome do dispositivo, fabricante, modelo, usuário, status, ação, visto pela última vez e histórico. Você pode personalizar a exibição para mostrar as informações que se ajustam às suas necessidades.

Telefones, Salas do Teams no Android, exibições do Teams e painéis do Teams são registrados automaticamente em Microsoft Intune se você se inscreveu para isso. Depois que um dispositivo é registrado, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

Aqui estão alguns exemplos de como você pode gerenciar telefones, Salas do Teams nos painéis Android, Teams e Teams em sua organização.  

| Para fazer isso...                           | Faça isso                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alterar informações do dispositivo               | Selecione um dispositivo > **Editar**. Você pode editar detalhes como nome do dispositivo, marca de ativo e adicionar anotações.                                                                                                                                                                                                              |
| Gerenciar atualizações de software                 | Selecione um dispositivo > **Atualizar**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a serem instaladas. Para obter mais informações sobre como atualizar dispositivos, consulte [Atualizar dispositivos do Teams remotamente](remote-update.md)                                                          |
| Atualizar telefones do Teams para exibições do Teams  | Na página **telefones IP** , selecione um ou mais telefones do Teams > **Atualizar**. Essa opção está disponível apenas para telefones que dão suporte à atualização para exibições do Teams. Para saber mais, confira [Atualizar telefones do Teams para exibições do Teams](upgrade-phones-to-displays.md).                                                      |
| Atribuir ou alterar políticas de configuração | Selecione um ou mais dispositivos > **Atribuir configuração**.                                                                                                                                                                                                                                                       |
| Adicionar ou remover marcas de dispositivo               | Selecione um ou mais dispositivos > **Gerenciar marcas**. Para obter mais informações sobre marcas de dispositivo, consulte [Gerenciar marcas de dispositivo do Teams](manage-device-tags.md).                                                                                                                                                                 |
| Reiniciar dispositivos                         | Selecione um ou mais dispositivos > **Reiniciar**.                                                                                                                                                                                                                                                                    |
| Filtrar dispositivos usando marcas de dispositivo        | Selecione o ícone de filtro, selecione o campo **Marca** , especifique uma marca de dispositivo para filtrar e selecione **Aplicar**. Para obter mais informações sobre como filtrar dispositivos usando marcas de dispositivo, consulte [Usar filtros para retornar dispositivos com uma marca específica](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Exibir histórico e diagnóstico do dispositivo     | Na coluna **Histórico** , clique no link **Exibir** para um dispositivo para exibir seu histórico de atualizações e detalhes de diagnóstico.                                                                                                                                                                                         |

### <a name="view-android-device-sign-in-failures"></a>Exibir falhas de entrada do dispositivo Android

Se você estiver tendo problemas para entrar em um dispositivo Android, poderá verificar a página de detalhes do dispositivo para ver quais falhas de entrada podem ter ocorrido.

1. Na navegação à esquerda, acesse **dispositivos do Teams** > selecione o tipo de dispositivo do Teams. Por exemplo, se o dispositivo Android for um telefone, selecione **Telefones**.
2. Clique no nome de exibição do Telefone para o qual você deseja exibir falhas de entrada. Isso abrirá a página de detalhes do dispositivo.
3. Na página de detalhes do dispositivo, selecione a guia **Atividade** e selecione **Falha de entrada** na lista suspensa **Tipo de atividade** .

> [!NOTE]
> Se você não vir nenhuma falha de entrada para um dispositivo em que está tendo problemas para entrar, verifique se o firmware do dispositivo está na versão mais recente fornecida pelo fabricante.

Os resultados retornados contêm as seguintes informações:

- A hora em que a falha de entrada ocorreu.
- A conta que tentou entrar no dispositivo.
- O motivo da falha.

### <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar configurações e recursos para diferentes dispositivos do Teams em sua organização, incluindo Salas do Teams nos painéis Android, Teams, Telefone do Teams e Teams. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou conjunto de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

Para criar um perfil de configuração para um tipo de dispositivo do Teams:

1. Na navegação à esquerda, acesse **Dispositivos do Teams** > selecione o tipo de dispositivo do Teams > **Perfis de configuração**. Por exemplo, selecione **Painéis do Teams Devices** > **Teams Perfis** > **de configuração** para criar um novo perfil de configuração para painéis do Teams.
2. Clique em **Adicionar**.
3. Insira um nome para o perfil e, opcionalmente, adicione uma descrição amigável.
4. Especifique as configurações desejadas para o perfil e clique em **Salvar**.
   O perfil de configuração recém-criado é exibido na lista de perfis.

#### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração

Depois de criar um perfil de configuração para um tipo de dispositivo do Teams, atribua-o a um ou mais dispositivos.

1. Na navegação à esquerda, acesse **Dispositivos do Teams** > selecione o tipo de dispositivo do Teams. Por exemplo, para atribuir um perfil de configuração a um dispositivo de painéis do Teams, selecione **Painéis do** **Teams Devices** >  Teams.
2. Selecione um ou mais dispositivos e clique em **Atribuir configuração**.  
3. No painel **Atribuir uma configuração** , pesquise o perfil de configuração a ser atribuído aos dispositivos selecionados.
4. Clique em **Aplicar**.
   Para os dispositivos aos quais você aplicou a política de configuração, a coluna **Ação** exibe **a Atualização de Configuração** e a coluna **Perfil de Configuração** exibe o nome do perfil de configuração.
