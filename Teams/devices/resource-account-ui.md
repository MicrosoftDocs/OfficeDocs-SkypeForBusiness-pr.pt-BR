---
title: Criar uma conta de recurso usando a Centro de administração do Microsoft 365
description: Se você preferir usar uma interface gráfica de usuário, poderá criar uma conta de recurso para suas barras de Salas do Microsoft Teams e colaboração para Microsoft Teams usando o Centro de Administração Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: criar conta de dispositivo, Microsoft 365 interface do usuário, Centro de administração do Microsoft 365
ms.sitesec: library
ms.service: msteams
author: cazawideh
ms.author: czawideh
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1d4d3a24222183c8798bb5d0e7eda879acca8d3e
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503938"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Criar uma Microsoft 365 de recursos usando a Centro de administração do Microsoft 365

Microsoft 365 contas de recursos são caixas de correio e Teams que são dedicadas a recursos específicos, como sala, projetor e assim por diante. Essas contas de recursos podem responder automaticamente a convites de reunião usando regras definidas quando elas são criadas. Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licenciamento

Antes de criar uma Microsoft 365 de recursos, verifique para ver de que tipo de licença ela precisa. Se você usar apenas uma conta de recurso para reservar um recurso (ou seja, convidar o recurso para sua reunião e aceitá-lo automaticamente ou recusar o convite), não será necessário atribuir uma licença a uma conta de recurso. Você precisará atribuir uma licença à conta de recurso nas seguintes situações:

- **Teams** reunião Se você quiser que o recurso (como um console de Salas do Microsoft Teams, uma barra de colaboração e assim por diante) participe de uma reunião do Teams para que os participantes possam usá-lo para apresentar vídeo e áudio por meio dele, você precisa de uma licença de Sala de Reunião. 
- **Chamadas PSTN** Se você quiser que o recurso faça ou receba chamadas para ou de um número de telefone externo (chamado de rede telefônica pública comutado ou chamada PSTN), você precisa de uma licença Microsoft 365 Sistema de Telefonia ou Microsoft 365 Business Voice pública.

Para obter mais informações sobre Sala de Reunião, Sistema de Telefonia e licenças do Business Voice, consulte [Microsoft Teams licenças de complemento](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Criar uma conta de recurso no Centro de administração do Microsoft 365

1. Entre no Microsoft 365 visitandohttps://admin.microsoft.com
2. Forneça as credenciais de administrador para seu Microsoft 365 locatário. Isso o levará ao seu Centro de administração do Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administração do Microsoft 365.":::
3. No centro de administração, navegue até **Recursos** no painel esquerdo (talvez seja necessário selecionar **Mostrar** tudo primeiro) e selecione **Salas & equipamento**.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administração do Microsoft 365 - Recursos.":::
4. Selecione **Adicionar uma caixa de correio de recurso** para criar uma nova conta de sala. Insira um nome de exibição e um endereço de email para a conta, selecione **Adicionar** e selecione **Fechar**. Recomendamos que você padronizar uma convenção de nomenisco para todas as suas contas de recursos.

> [!NOTE]
> Por padrão, as contas de recursos são configuradas com as seguintes configurações. Se quiser alterá-las, selecione **Definir opções de agendamento** antes de selecionar **Fechar**. Se você quiser alterá-los posteriormente, navegue até **ResourcesRooms** >  & equipamento, selecione a conta de recurso e selecione **Editar** em **Opções de Reserva**.
>
> - Permitir reuniões repetidas
> - Recusar reuniões automaticamente fora dos limites a seguir
>   - Janela de reserva (dias): 180
>   - Duração máxima (horas): 24
> - Solicitações de reunião de aceitação automática

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administração do Microsoft 365 - Adicionar recursos.":::
5. Navegue até **a seção Usuários** no centro de administração e,  na lista Usuários ativos, você verá a sala que acabou de criar.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administração do Microsoft 365 - Consulte usuários ativos.":::
6. Selecione o nome da sala e um painel de propriedades da conta aparecerá à direita.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administração do Microsoft 365 - Propriedades do usuário.":::
7. Agora você precisa atribuir uma senha à conta de recurso. No painel, você pode ver as propriedades da conta e várias ações opcionais. Selecione o **ícone Redefinir a chave** de senha no nome de usuário para alterar a senha. **Desmarcar Exigir que esse usuário altere a senha quando entrar pela primeira vez**. Não é possível alterar a senha por meio do processo de entrada do dispositivo. Selecione **Redefinir**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administração do Microsoft 365 - Redefinir senha.":::
8. Na seção **Licenças e Aplicativos** , de definir **Selecionar local** para o país ou região onde o dispositivo será instalado. Role para baixo e marque a caixa ao lado da licença a ser atribuída - como Sala de Reunião - e selecione **Salvar alterações**. A licença pode variar dependendo da sua organização.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administração do Microsoft 365 - Atribuir licença.":::
