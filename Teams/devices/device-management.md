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
description: Saiba como gerenciar dispositivos usados com o Microsoft Teams em sua organização.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033022"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gerenciar seus dispositivos no Microsoft Teams

Você pode gerenciar os dispositivos usados com o Microsoft Teams em sua organização usando o centro de administração do Microsoft Teams. Você pode exibir e gerenciar o inventário de dispositivos da sua organização e executar tarefas como atualizar, reiniciar e monitorar o diagnóstico de dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.

Para gerenciar dispositivos, como alterar a configuração do dispositivo, reiniciar dispositivos, gerenciar atualizações ou exibir a integridade do dispositivo e do periférico, você precisa receber uma das seguintes funções de administração do Microsoft 365:

- Administrador global do Microsoft 365
- Administrador do teams Service
- Administrador de dispositivos do teams

Para obter mais informações sobre funções de administrador no Teams, consulte [usar funções de administrador do teams para gerenciar o Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?

Você pode gerenciar qualquer dispositivo certificado e inscrito no Microsoft Teams. Um dispositivo é registrado automaticamente na primeira vez que o usuário entra no Microsoft Teams no dispositivo. Para obter uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Salas do Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams exibe](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barras de colaboração](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Para gerenciar dispositivos, na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com), vá para **dispositivos** e selecione o tipo de dispositivo. Cada tipo de dispositivo tem sua própria seção respectiva, que permite que você o gerencie separadamente.

## <a name="manage-teams-rooms-devices"></a>Gerenciar dispositivos de salas de equipe

Você pode usar o centro de administração do teams para exibir e gerenciar remotamente seus dispositivos de salas de equipe em sua organização. O centro de administração do Microsoft Teams torna mais fácil ver, em um relance, quais dispositivos estão íntegros e quais precisam de atenção e permitem que você se concentre em dispositivos específicos para ver informações detalhadas sobre a integridade do dispositivo, o desempenho da reunião, a qualidade da chamada e periféricos. 

Aqui estão algumas coisas que você pode fazer para gerenciar seus dispositivos de sala de equipe. Os dispositivos de salas de equipe podem ser encontrados no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) em salas de equipe de **dispositivos**  >  **Teams Rooms**.

Para obter detalhes sobre como gerenciar seus dispositivos de salas de equipe, consulte [gerenciar salas do Microsoft Teams](../rooms/rooms-manage.md).

| Para fazer isso... | Faça isto|
|---------------|--------|
| Alterar configurações em um ou mais dispositivos | Selecione um ou mais dispositivos > **Editar configurações**. Se você selecionar vários dispositivos, os valores alterados substituirão os valores em todos os dispositivos selecionados. |
| Reiniciar dispositivos | Selecione um ou mais dispositivos > **reiniciar**. Ao reiniciar um dispositivo, você pode escolher se deseja reiniciar o dispositivo imediatamente ou selecionar **agendar reinicialização** para reiniciar o dispositivo em uma data e hora específicas. A data e a hora selecionadas são locais para o dispositivo que está sendo reiniciado.|
| Exibir atividade da reunião | Selecione um nome de dispositivo para abrir detalhes do dispositivo > **atividade**. Ao abrir a guia **atividade** , você pode ver todas as reuniões nas quais o dispositivo participou. Este modo de exibição de resumo mostra a hora de início da reunião, o número de participantes, sua duração e a qualidade geral da chamada.|
| Ver detalhes da reunião |  Selecione um nome de dispositivo para abrir detalhes do dispositivo > **atividade** > selecione uma reunião. Ao abrir os dados de uma reunião, você pode ver todos os participantes da reunião, por quanto tempo eles estavam na chamada, os tipos de sessão do Team e a qualidade da chamada individual. Se você quiser ver informações técnicas sobre a chamada de um participante, selecione a hora de início da chamada do participante.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Gerenciar telefones, barras de colaboração e telas do teams 

No centro de administração do Teams, você pode exibir e gerenciar telefones, barras de colaboração e exibições de equipes registrados no Microsoft Teams em sua organização. As informações que você verá para cada dispositivo inclui o nome do dispositivo, o fabricante, o modelo, o usuário, o status, a ação, o último visto e o histórico. Você pode personalizar o modo de exibição para mostrar as informações que atendem às suas necessidades.

Telefones, barras de colaboração e exibições de equipes são automaticamente registrados no Microsoft Intune se você se inscreveu para ele. Depois que um dispositivo é registrado, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

Aqui estão alguns exemplos de como você pode gerenciar telefones, barras de colaboração e telas de equipe em sua organização.  

|Para fazer isso...  |Faça isto |
|---------|---------|
| Alterar as informações do dispositivo               | Selecione um dispositivo > **Editar**. Você pode editar detalhes, como o nome do dispositivo, a marca de ativos e adicionar anotações.     |
| Gerenciar atualizações de software                 | Selecione um dispositivo > **atualização**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a serem instaladas. Para obter mais informações sobre como atualizar dispositivos, consulte [Atualizar dispositivos de equipe remotamente](remote-update.md)   |
| Atualizar telefones de equipes para o Microsoft Teams                | Na página **IP phones** , selecione um ou mais grupos de telefones > **atualização**. Essa opção está disponível somente para telefones que oferecem suporte à atualização para o Microsoft Teams. Para saber mais, confira [atualizar os telefones de equipes para o Microsoft Teams](upgrade-phones-to-displays.md).   |
| Atribuir ou alterar políticas de configuração | Selecione um ou mais dispositivos > **atribuir configuração**.                                                                                                                                                                                                                   |
| Adicionar ou remover marcas de dispositivo               | Selecione um ou mais dispositivos > **gerenciar marcas**. Para obter mais informações sobre marcas de dispositivo, consulte [gerenciar marcas de dispositivo do teams](manage-device-tags.md).                                                                                                      |
| Reiniciar dispositivos                         | Selecione um ou mais dispositivos > **reiniciar**.                                                                                                                                                                                                                                |
| Filtrar dispositivos usando marcas de dispositivo        | Selecione o ícone de filtro, selecione o campo de **marca** , especifique uma marca de dispositivo para filtrar e selecione **aplicar**. Para obter mais informações sobre como filtrar dispositivos usando marcas de dispositivo, consulte [usar filtros para retornar dispositivos com uma marca específica](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).|
| Exibir o histórico de dispositivos                     | Selecione um > **histórico** de dispositivos. Você pode exibir o histórico de atualizações do dispositivo.                                                                                                                                                                                |
| Exibir diagnósticos                        | Selecione um dispositivo > **diagnóstico**.                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar as configurações e os recursos de telefones e barras de colaboração de equipes em sua organização. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que você deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou grupos de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

1. No painel de navegação esquerdo, vá para perfis de configuração de **dispositivos**  >  **Configuration profiles**.
2. Clique em **Adicionar**.
3. Digite um nome para o perfil e, se desejar, adicione uma descrição amigável.
4. Especifique as configurações desejadas para o perfil e clique em **salvar**.

#### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração

1. No painel de navegação esquerdo, vá para perfis de configuração de **dispositivos**  >  **Configuration profiles**.
2. Selecione o **perfil de configuração** que você deseja atribuir e clique em **atribuir a dispositivo**.  
3. No painel **atribuir dispositivos a um perfil de configuração** , procure e selecione os dispositivos que você deseja atribuir.
4. Clique em **Salvar**.

