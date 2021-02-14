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
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033022"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gerenciar seus dispositivos no Microsoft Teams

Você pode gerenciar os dispositivos usados com o Microsoft Teams em sua organização a partir do Centro de administração do Microsoft Teams. Você pode exibir e gerenciar o inventário de dispositivos da sua organização e realizar tarefas como atualizar, reiniciar e monitorar diagnósticos para dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.

Para gerenciar dispositivos, como alterar a configuração do dispositivo, reiniciar dispositivos, gerenciar atualizações ou exibir o dispositivo e a saúde periférico, você precisa ter uma das seguintes funções de administrador do Microsoft 365:

- Administrador global do Microsoft 365
- Administrador do Serviço do Teams
- Administrador de dispositivo do Teams

Para obter mais informações sobre funções de administrador no Teams, [consulte Usar funções de administrador do Teams para gerenciar o Teams.](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?

Você pode gerenciar qualquer dispositivo certificado e inscrito no Teams. Um dispositivo é automaticamente inscrito na primeira vez que um usuário entrar no Teams no dispositivo. Para ver uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Salas do Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [O Teams é exibido](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barras de colaboração](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Para gerenciar dispositivos, na navegação à esquerda do Centro de administração do [Microsoft Teams,](https://admin.teams.microsoft.com)vá para Dispositivos e **selecione** o tipo de dispositivo. Cada tipo de dispositivo tem sua própria seção respectiva, que permite gerenciá-los separadamente.

## <a name="manage-teams-rooms-devices"></a>Gerenciar dispositivos de Salas do Teams

Você pode usar o Centro de administração do Teams para exibir e gerenciar remotamente seus dispositivos de Salas do Teams em toda a organização. O Centro de administração do Teams facilita a visão, num relance, de quais dispositivos são saudáveis e que precisam de atenção e permite que você se concentre em dispositivos específicos para ver informações detalhadas sobre a saúde do dispositivo, o desempenho da reunião, a qualidade da chamada e os periféricos. 

Veja algumas coisas que você pode fazer para gerenciar seus dispositivos de Salas do Teams. Os dispositivos de Salas do Teams podem ser encontrados no Centro de [administração do Microsoft Teams](https://admin.teams.microsoft.com) em Salas do   >  **Teams.**

Para obter detalhes sobre como gerenciar seus dispositivos de Salas do Teams, consulte [Gerenciar Salas do Microsoft Teams.](../rooms/rooms-manage.md)

| Para fazer isso... | Faça isto|
|---------------|--------|
| Alterar configurações em um ou mais dispositivos | Selecione um ou mais dispositivos > **Editar configurações.** Se você selecionar vários dispositivos, os valores que você alterar substituirão os valores em todos os dispositivos selecionados. |
| Reiniciar dispositivos | Selecione um ou mais dispositivos > **Reiniciar.** Ao reiniciar um dispositivo, você pode optar por  reiniciar o dispositivo imediatamente ou selecionar Agendar reinicialização para reiniciar o dispositivo em uma data e hora específicas. A data e a hora selecionadas são locais para o dispositivo que está sendo reiniciado.|
| Exibir atividade da reunião | Selecione um nome de dispositivo para abrir detalhes do dispositivo > **Atividade.** Ao abrir a **guia Atividade,** você pode ver todas as reuniões em que o dispositivo participou. Esse modo de exibição de resumo mostra a hora de início da reunião, o número de participantes, sua duração e a qualidade geral da chamada.|
| Exibir detalhes da reunião |  Selecione um nome de dispositivo para abrir detalhes do dispositivo > **Atividade** > uma reunião. Ao abrir os detalhes de uma reunião, você pode ver todos os participantes da reunião, quanto tempo eles estavam na chamada, os tipos de sessão do Teams e sua qualidade de chamada individual. Se você quiser ver informações técnicas sobre a chamada de um participante, selecione a hora de início da chamada do participante.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Gerenciar telefones, barras de colaboração e exibições do Teams 

No Centro de administração do Teams, você pode exibir e gerenciar telefones, barras de colaboração e o Teams exibe os grupos inscritos no Teams em sua organização. As informações que você verá para cada dispositivo incluem nome do dispositivo, fabricante, modelo, usuário, status, ação, visto pela última vez e histórico. Você pode personalizar o exibição para mostrar as informações que adem suas necessidades.

Telefones, barras de colaboração e exibições do Teams são automaticamente inscritos no Microsoft Intune se você se inscreveu. Depois que um dispositivo é inscrito, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

Aqui estão alguns exemplos de como você pode gerenciar telefones, barras de colaboração e exibições do Teams em sua organização.  

|Para fazer isso...  |Faça isto |
|---------|---------|
| Alterar informações do dispositivo               | Selecione um dispositivo > **Editar.** Você pode editar detalhes como nome do dispositivo, marca de ativos e adicionar anotações.     |
| Gerenciar atualizações de software                 | Selecione um dispositivo > **Atualizar.** Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a instalar. Para obter mais informações sobre como atualizar dispositivos, consulte [Atualizar dispositivos do Teams remotamente](remote-update.md)   |
| Atualizar telefones do Teams para exibições do Teams                | Na página **telefones IP,** selecione um ou mais telefones do Teams > **Atualizar.** Essa opção só está disponível para telefones que suportam a atualização para as exibições do Teams. Para saber mais, confira [a exibição Atualizar telefones do Teams para o Teams.](upgrade-phones-to-displays.md)   |
| Atribuir ou alterar políticas de configuração | Selecione um ou mais dispositivos > **atribuir configuração.**                                                                                                                                                                                                                   |
| Adicionar ou remover marcas de dispositivo               | Selecione um ou mais dispositivos > **Gerenciar marcas.** Para obter mais informações sobre marcas de dispositivo, consulte [Gerenciar marcas de dispositivo do Teams.](manage-device-tags.md)                                                                                                      |
| Reiniciar dispositivos                         | Selecione um ou mais dispositivos > **Reiniciar.**                                                                                                                                                                                                                                |
| Filtrar dispositivos usando marcas de dispositivo        | Selecione o ícone de filtro, selecione **o** campo Marca, especifique uma marca de dispositivo para filtrar e selecione **Aplicar.** Para obter mais informações sobre filtragem de dispositivos usando marcas de dispositivo, [consulte Usar filtros para retornar dispositivos com uma marca específica.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)|
| Exibir histórico de dispositivos                     | Selecione um histórico > **dispositivo.** Você pode exibir o histórico de atualizações do dispositivo.                                                                                                                                                                                |
| Exibir diagnóstico                        | Selecione um dispositivo > **Diagnóstico.**                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar configurações e recursos para telefones do Teams e barras de colaboração em sua organização. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou grupos de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

1. Na navegação à esquerda, vá para **perfis de**  >  **Configuração de Dispositivos.**
2. Clique em **Adicionar**.
3. Insira um nome para o perfil e, se quiser, adicione uma descrição amigável.
4. Especifique as configurações que você deseja para o perfil e clique em **Salvar.**

#### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração

1. Na navegação à esquerda, vá para **perfis de**  >  **Configuração de Dispositivos.**
2. Selecione o **perfil de configuração** que você deseja atribuir e clique em **Atribuir ao dispositivo.**  
3. No painel **Atribuir dispositivos a um** perfil de configuração, pesquise e selecione os dispositivos que você deseja atribuir.
4. Clique em **Salvar**.

