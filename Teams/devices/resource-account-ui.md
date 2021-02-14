---
title: Criar uma conta de recurso usando o Centro de administração do Microsoft 365
description: Se preferir usar uma interface gráfica do usuário, você pode criar uma conta de recurso para suas Salas do Microsoft Teams e barras de colaboração para o Microsoft Teams usando o Centro de Administração do Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: criar conta de dispositivo, Interface do Usuário do Microsoft 365, Centro de administração do Microsoft 365
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268006"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Criar uma conta de recurso do Microsoft 365 usando o Centro de administração do Microsoft 365

As contas de recursos do Microsoft 365 são caixas de correio e contas do Teams dedicadas a recursos específicos, como uma sala, projetor e assim por diante. Essas contas de recurso podem responder automaticamente a convites de reunião usando regras definidas quando elas são criadas. Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licenciamento

Antes de criar uma conta de recurso do Microsoft 365, verifique que tipo de licença ela precisa. Se você só usar uma conta de recurso para reservar um recurso (ou seja, convidar o recurso para sua reunião e fazer com que ele aceite ou re decline automaticamente o convite), não será necessário atribuir uma licença a uma conta de recurso. Você precisará atribuir uma licença à conta de recurso nas seguintes situações:

- **Reunião do Teams** Se você quiser que o recurso (como um console de Salas do Microsoft Teams, uma barra de colaboração e assim por diante) in join a uma reunião do Teams para que os participantes possam usá-lo para apresentar vídeo e áudio por meio dele, você precisará de uma licença de Sala de Reunião. 
- **Chamadas PSTN** Se quiser que o recurso faça ou receba chamadas para ou de um número de telefone externo (chamado de Rede Telefônica Pública Comutado ou chamada PSTN), você precisará de uma licença do Microsoft 365 Phone System ou do Microsoft 365 Business Voice.

Para obter mais informações sobre licenças de Sala de Reunião, Sistema de Telefonia e Voz Comercial, consulte licenças de complemento [do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Criar uma conta de recurso no Centro de administração do Microsoft 365

1. Entre no Microsoft 365 visitando https://admin.microsoft.com
2. Forneça as credenciais de administrador para seu locatário do Microsoft 365. Isso o levará para o centro de administração do Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administração do Microsoft 365":::
3. No centro de administração, navegue até Recursos no  painel esquerdo (talvez seja necessário selecionar Mostrar tudo primeiro) e selecione Salas **& equipamento.** 

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administração do Microsoft 365 - Recursos":::
4. Selecione **Adicionar uma caixa de correio de recurso** para criar uma nova conta de sala. Insira um nome de exibição e um endereço de email para a conta, selecione **Adicionar** e, em seguida, selecione **Fechar.** Recomendamos que você padronizar uma convenção de nomen– para todas as suas contas de recursos.

> [!NOTE]
> Por padrão, as contas de recurso são configuradas com as seguintes configurações. Se quiser alterá-las, selecione **Definir opções de agendamento** antes de selecionar **Fechar.** Se quiser alterá-las mais tarde, navegue até Salas de Recursos & equipamento, selecione a conta de recurso e selecione  >   **Editar** em Opções **de Reserva.**
>
> - Permitir reuniões repetidas
> - Recusar reuniões automaticamente fora dos limites a seguir
>   - Janela de reserva (dias): 180
>   - Duração máxima (horas): 24
> - Aceitar automaticamente solicitações de reunião

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administração do Microsoft 365 - Adicionar recursos":::
5. Navegue até **a seção** Usuários no  centro de administração e, na lista usuários ativos, você verá a sala que acabou de criar.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administração do Microsoft 365 - Ver usuários ativos":::
6. Selecione o nome da sala e o painel de propriedades da conta aparecerá à direita.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administração do Microsoft 365 - Propriedades do usuário":::
7. Agora você precisa atribuir uma senha à conta de recurso. No painel, você pode ver as propriedades da conta e várias ações opcionais. Selecione o **ícone redefinir** senha sob o nome de usuário para alterar a senha. Desmarque **Exigir que este usuário altere a senha ao entrar pela primeira vez.** Não é possível alterar a senha por meio do processo de entrada do dispositivo. Selecione **Redefinir.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administração do Microsoft 365 - Redefinir senha":::
8. Na seção **Licenças e Aplicativos,** deverão definir **o** local de seleção para o país ou a região onde o dispositivo será instalado. Role para baixo e marque a caixa ao lado da licença a ser atribuída, como Sala de Reunião, e selecione **Salvar alterações.** A licença pode variar dependendo da sua organização.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administração do Microsoft 365 – Atribuir licença":::
