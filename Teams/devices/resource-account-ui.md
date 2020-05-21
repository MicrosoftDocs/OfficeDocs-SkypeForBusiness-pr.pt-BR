---
title: Criar uma conta de recurso usando o centro de administração do Microsoft 365
description: Se preferir usar uma interface gráfica de usuário, você poderá criar uma conta de recurso para as salas e as barras de colaboração do Microsoft Teams do Microsoft Teams usando o centro de administração do Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: criar conta de dispositivo, interface do usuário do Microsoft 365, centro de administração do Microsoft 365
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="dd900-104">Criar uma conta de recurso do Microsoft 365 usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd900-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="dd900-105">As contas de recursos do Microsoft 365 são contas de caixa de correio e de equipe dedicadas a recursos específicos, como uma sala, um projetor e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="dd900-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="dd900-106">Essas contas de recursos podem responder automaticamente aos convites de reunião usando regras definidas quando são criadas.</span><span class="sxs-lookup"><span data-stu-id="dd900-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="dd900-107">Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário.</span><span class="sxs-lookup"><span data-stu-id="dd900-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="dd900-108">Licenças</span><span class="sxs-lookup"><span data-stu-id="dd900-108">Licensing</span></span>

<span data-ttu-id="dd900-109">Antes de criar uma conta de recurso do Microsoft 365, verifique o tipo de licença necessário.</span><span class="sxs-lookup"><span data-stu-id="dd900-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="dd900-110">Se você usar apenas uma conta do recurso para agendar um recurso (ou seja, convidar o recurso para a reunião e ele aceitar ou recusar o convite automaticamente), você não precisará atribuir uma licença a uma conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="dd900-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="dd900-111">Você precisará atribuir uma licença para a conta do recurso nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="dd900-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="dd900-112">**Reunião do teams** Se você quiser que o recurso (como um console de salas do Microsoft Teams, barra de colaboração e assim por diante) ingresse em uma reunião de equipe para que os participantes possam usá-lo para apresentar vídeo e áudio por meio dele, você precisará de uma licença de sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="dd900-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="dd900-113">**Chamadas PSTN** Se quiser que o recurso faça ou receba chamadas para ou de um número de telefone externo (chamado de uma rede telefônica pública comutada ou chamada PSTN), você precisará de um sistema telefônico Microsoft 365 ou da licença de voz do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="dd900-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="dd900-114">Para obter mais informações sobre sala de reunião, sistema telefônico e licenças de voz para empresas, consulte [licenças de Complementos do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="dd900-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="dd900-115">Criar uma conta de recurso no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd900-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="dd900-116">Acesse o Microsoft 365 visitandohttps://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dd900-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="dd900-117">Forneça as credenciais de administrador para o seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd900-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="dd900-118">Isso o levará ao centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd900-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administração do Microsoft 365":::
3. <span data-ttu-id="dd900-120">No centro de administração, navegue até **recursos** no painel esquerdo (talvez seja necessário selecionar **Mostrar todos os** primeiros) e, em seguida, selecione **salas & equipamento**.</span><span class="sxs-lookup"><span data-stu-id="dd900-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administração do Microsoft 365-recursos":::
4. <span data-ttu-id="dd900-122">Selecione **Adicionar uma caixa de correio de recurso** para criar uma nova conta de sala.</span><span class="sxs-lookup"><span data-stu-id="dd900-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="dd900-123">Digite um nome de exibição e um endereço de email para a conta, selecione **Adicionar**e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="dd900-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="dd900-124">Recomendamos que você padronize uma Convenção de nomenclatura para todas as suas contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="dd900-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="dd900-125">Por padrão, as contas de recurso são definidas com as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd900-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="dd900-126">Se desejar alterá-los, selecione **definir opções de agendamento** antes de selecionar **fechar**.</span><span class="sxs-lookup"><span data-stu-id="dd900-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="dd900-127">Se desejar alterá-los mais tarde, navegue até salas de **recursos**  >  **& equipamento**, selecione a conta do recurso e, em seguida, selecione **Editar** em **Opções de reserva**.</span><span class="sxs-lookup"><span data-stu-id="dd900-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="dd900-128">Permitir repetição de reuniões</span><span class="sxs-lookup"><span data-stu-id="dd900-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="dd900-129">Recusar reuniões automaticamente fora dos seguintes limites</span><span class="sxs-lookup"><span data-stu-id="dd900-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="dd900-130">Janela de reserva (dias): 180</span><span class="sxs-lookup"><span data-stu-id="dd900-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="dd900-131">Duração máxima (horas): 24</span><span class="sxs-lookup"><span data-stu-id="dd900-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="dd900-132">Aceitar solicitações de reunião automaticamente</span><span class="sxs-lookup"><span data-stu-id="dd900-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administração do Microsoft 365 – adicionar recursos":::
5. <span data-ttu-id="dd900-134">Navegue até a seção **usuários** no centro de administração e, na lista **usuários ativos** , você verá a sala que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="dd900-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administração do Microsoft 365-ver usuários ativos":::
6. <span data-ttu-id="dd900-136">Selecione o nome da sala e um painel de propriedades da conta será exibido à direita.</span><span class="sxs-lookup"><span data-stu-id="dd900-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administração do Microsoft 365 – Propriedades do usuário":::
7. <span data-ttu-id="dd900-138">Agora, você precisa atribuir uma senha à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="dd900-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="dd900-139">No painel, você pode ver as propriedades da conta e várias ações opcionais.</span><span class="sxs-lookup"><span data-stu-id="dd900-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="dd900-140">Selecione o ícone redefinir chave da **senha** abaixo do nome de usuário para alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="dd900-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="dd900-141">Desmarque **exigir que este usuário altere a senha quando entrarem pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="dd900-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="dd900-142">Não é possível alterar a senha por meio do processo de entrada do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dd900-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="dd900-143">Selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="dd900-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administração do Microsoft 365-Redefinir senha":::
8. <span data-ttu-id="dd900-145">Na seção **licenças e aplicativos** , defina **selecionar local** para o país ou a região onde o dispositivo será instalado.</span><span class="sxs-lookup"><span data-stu-id="dd900-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="dd900-146">Role a tela para baixo e marque a caixa ao lado da licença a ser atribuída, como sala de reunião, e escolha **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="dd900-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="dd900-147">A licença pode variar dependendo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="dd900-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administração do Microsoft 365-atribuir licença":::