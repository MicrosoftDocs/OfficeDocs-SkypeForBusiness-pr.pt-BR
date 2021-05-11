---
title: Mover usuários do ambiente local para o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Saiba como mover os usuários para Skype for Business Online.
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305975"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="e1bfa-103">Mover usuários do ambiente local para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e1bfa-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="e1bfa-104">Depois de mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business Online para sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="e1bfa-105">Todos os contatos existentes no local estarão disponíveis no Skype for Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro serão atualizadas para que os links apontem para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="e1bfa-106">Se o usuário estiver habilitado para Audioconferência, as reuniões também incluirão coordenadas discada.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="e1bfa-107">Para mover usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o painel de controle Skype for Business Server, ambos são ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e1bfa-108">Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="e1bfa-109">Em preparação para a próxima reforma do Skype for Business Online, a Microsoft estará simplificando como as organizações se movem para o Teams em um futuro próximo e não será mais possível mover para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future and it will no longer be possible to move to Skype for Business Online.</span></span>  <span data-ttu-id="e1bfa-110">Quando essas alterações são disponibilizadas, ao mover um usuário do local para a nuvem, os usuários serão atribuídos automaticamente ao modo TeamsOnly e suas reuniões no local serão convertidas automaticamente em reuniões Teams, como se a opção tivesse sido especificada, independentemente de a opção ser realmente `-MoveToTeams` especificada.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-110">Once these changes are made available, when moving a user from on-premises to the cloud, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="e1bfa-111">Esperamos lançar essa funcionalidade antes da aposentadoria real de 31 de julho de 2021.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-111">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>   <span data-ttu-id="e1bfa-112">No momento, se essa opção não for especificada, os usuários migram de uma residência no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado, que é a funcionalidade documentada neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-112">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged, which is the functionality documented in this article.</span></span>

 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="e1bfa-113">Mover usuários com Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e1bfa-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="e1bfa-114">Move-CsUser está disponível em uma janela local Skype for Business Shell de Gerenciamento do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="e1bfa-115">Você deve ter privilégios suficientes no ambiente local, bem como na organização Microsoft 365, conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="e1bfa-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e1bfa-116">Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta Microsoft 365 com a função administrativa `-Credential` necessária.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="e1bfa-117">Para mover um usuário para online usando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="e1bfa-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="e1bfa-118">Especifique o usuário para mover usando o parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="e1bfa-119">Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="e1bfa-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e1bfa-120">Se você não tiver uma conta com permissões suficientes no local e Microsoft 365, use o parâmetro -credential para fornecer uma conta com permissões suficientes Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="e1bfa-121">Se a conta com permissões no Microsoft 365 não terminar em ".onmicrosoft. <span> com", em seguida, você deve especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="e1bfa-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="e1bfa-122">A sequência de cmdlets a seguir pode ser usada para mover um usuário para Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-122">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="e1bfa-123">Presume que a credencial Microsoft 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="e1bfa-124">Se a conta de administrador estiver habilitada para MFA (Autenticação Multifa factor), não especifique o parâmetro -Credential.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="e1bfa-125">O administrador será solicitado a solicitar credenciais.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e1bfa-126">Mover usuários com Skype for Business Server Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="e1bfa-126">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="e1bfa-127">Abra o aplicativo Skype for Business Server Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e1bfa-128">Na navegação à esquerda, escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e1bfa-129">Use **Localizar** para localizar os usuários que você gostaria de mover para Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="e1bfa-130">Selecione o(s) usuário(s) e, em seguida, no menu suspenso **Ação** acima da lista, escolha Mover usuários selecionados para Skype for Business **Online**.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="e1bfa-131">No assistente, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-131">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e1bfa-132">Se solicitado, entre no Microsoft 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-132">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e1bfa-133">Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-133">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e1bfa-134">Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.</span><span class="sxs-lookup"><span data-stu-id="e1bfa-134">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1bfa-135">Também consulte</span><span class="sxs-lookup"><span data-stu-id="e1bfa-135">See also</span></span>

[<span data-ttu-id="e1bfa-136">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e1bfa-136">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
