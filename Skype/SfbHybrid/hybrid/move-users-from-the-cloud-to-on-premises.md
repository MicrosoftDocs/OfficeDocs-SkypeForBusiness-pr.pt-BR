---
title: Mover usuários da nuvem para o local
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
description: Saiba como mover usuários do Skype for Business Online para o local.
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110607"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="ca295-103">Mover usuários da nuvem para o local</span><span class="sxs-lookup"><span data-stu-id="ca295-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="ca295-104">Se necessário, você pode mover um usuário que foi migrado anteriormente do local para a nuvem (usando o Skype for Business Online ou Somente o Teams) de volta para o local.</span><span class="sxs-lookup"><span data-stu-id="ca295-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="ca295-105">Para mover os usuários do modo Skype for Business Online ou teamsOnly de volta para uma implantação local do Skype for Business Server, use o cmdlet Move-CsUser ou o Painel de Controle do Skype for Business Server, ambos eles são ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="ca295-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="ca295-106">Ao mover um usuário de volta para uma implantação local, você deve decidir para qual pool mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="ca295-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="ca295-107">Se o usuário estava anteriormente no modo TeamsOnly e você está usando uma versão anterior do Skype for Business Server 2015 com CU8, você também deve remover a atribuição do modo TeamsOnly do TeamsUpgradePolicy para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="ca295-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="ca295-108">Os usuários locais não devem ter mode= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ca295-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="ca295-109">As versões subsequentes do Skype for Business Server removem automaticamente essa atribuição.</span><span class="sxs-lookup"><span data-stu-id="ca295-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="ca295-110">Para obter mais detalhes, [consulte Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).</span><span class="sxs-lookup"><span data-stu-id="ca295-110">For more details, see [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca295-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ca295-111">Prerequisites</span></span>

- <span data-ttu-id="ca295-112">A organização deve ter o Azure AD Connect configurado corretamente e estar sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configure Azure AD Connect](configure-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="ca295-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="ca295-113">O usuário que está sendo movido de volta online para o local já deve existir no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="ca295-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="ca295-114">O Skype for Business híbrido deve ser configurado, conforme descrito em [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="ca295-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="ca295-115">Mover os usuários de volta para o local</span><span class="sxs-lookup"><span data-stu-id="ca295-115">Moving users back to on-premises</span></span>

<span data-ttu-id="ca295-116">Depois de mover um usuário da nuvem de volta para o local:</span><span class="sxs-lookup"><span data-stu-id="ca295-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="ca295-117">O usuário interage com sua implantação do Skype for Business Server para sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ca295-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="ca295-118">Todos os contatos existentes no Skype for Business Online ou no Teams são migrados para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca295-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="ca295-119">Os dois conjuntos de contatos são mesclados e migrados de volta para o local.</span><span class="sxs-lookup"><span data-stu-id="ca295-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="ca295-120">Além disso, os contatos pré-existentes no Teams permanecem no Teams.</span><span class="sxs-lookup"><span data-stu-id="ca295-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="ca295-121">Se o usuário também usa o Teams, ele não terá a capacidade de interoperar com usuários do Skype for Business, nem poderá se comunicar com usuários em organizações federadas.</span><span class="sxs-lookup"><span data-stu-id="ca295-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="ca295-122">As reuniões no Skype for Business Online não *são* migradas automaticamente para o local.</span><span class="sxs-lookup"><span data-stu-id="ca295-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="ca295-123">Os usuários devem reagendar suas reuniões ou, se desejado, usar a [Ferramenta de Migração de Reunião.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)</span><span class="sxs-lookup"><span data-stu-id="ca295-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="ca295-124">Mover usuários com Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ca295-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="ca295-125">Move-CsUser está disponível em uma janela local do Shell de Gerenciamento do Skype for Business PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca295-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="ca295-126">Você deve ter privilégios suficientes no ambiente local, bem como na organização do serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em [Credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)necessárias.</span><span class="sxs-lookup"><span data-stu-id="ca295-126">You must have sufficient privileges in both the on-premises environment as well as the cloud service organization (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="ca295-127">Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela do Shell de Gerenciamento do Skype for Business Server local com credenciais locais e usar o parâmetro para especificar credenciais para uma conta do `-Credential` Microsoft 365 ou office 365 com a função administrativa necessária.</span><span class="sxs-lookup"><span data-stu-id="ca295-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="ca295-128">Para mover um usuário para o local usando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ca295-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="ca295-129">Especifique o usuário para mover usando o parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="ca295-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="ca295-130">Especifique o parâmetro -Target com o nome de domínio totalmente qualificado do pool local desejado que hospedará o usuário.</span><span class="sxs-lookup"><span data-stu-id="ca295-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="ca295-131">Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365 ou Office 365), use o parâmetro -credential para fornecer uma conta com permissões suficientes no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca295-131">If you do not have one account with sufficient permissions in both on-premises and the cloud service (Microsoft 365 or Office 365), use the -credential parameter to supply an account with sufficient permissions in Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="ca295-132">Se a conta com permissões no Microsoft 365 ou no Office 365 não terminar em "on.microsoft.com", você deverá especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em [Credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)necessárias.</span><span class="sxs-lookup"><span data-stu-id="ca295-132">If the account with permissions in Microsoft 365 or Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="ca295-133">A sequência de cmdlets a seguir pode ser usada para mover um usuário para o Skype for Business Server e assume que a credencial do Microsoft 365 ou office 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="ca295-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="ca295-134">Mover usuários com o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ca295-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ca295-135">Abra o aplicativo Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca295-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="ca295-136">Na navegação à esquerda, escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ca295-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="ca295-137">Use **Localizar** para localizar os usuários que você gostaria de mover de volta para o local.</span><span class="sxs-lookup"><span data-stu-id="ca295-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="ca295-138">Selecione os usuários e, em seguida, na lista suspenso **Ação** acima da lista, escolha Mover usuários **selecionados** para o local .</span><span class="sxs-lookup"><span data-stu-id="ca295-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="ca295-139">No assistente, selecione o pool de usuários que hospedará o usuário e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ca295-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="ca295-140">Se solicitado, entre no Microsoft 365 ou Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="ca295-140">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="ca295-141">Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="ca295-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="ca295-142">Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.</span><span class="sxs-lookup"><span data-stu-id="ca295-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="ca295-143">Removendo o modo TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="ca295-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="ca295-144">Se você estiver usando uma versão anterior ao Skype for Business 2015 com CU8 e o usuário estiver sendo movido de volta para o local no modo TeamsOnly, você deverá remover a instância UpgradeToTeams antes de mover o usuário `TeamsUpgradePolicy` no local.</span><span class="sxs-lookup"><span data-stu-id="ca295-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="ca295-145">Você pode conceder explicitamente uma política com um modo diferente ou simplesmente remover a atribuição de política existente para que esse usuário use a política global (desde que a política global do locatário não seja UpgradeToTeams).</span><span class="sxs-lookup"><span data-stu-id="ca295-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="ca295-146">Para remover a atribuição do usuário do TeamsUpgradePolicy, execute o seguinte cmdlet de uma janela do PowerShell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="ca295-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="ca295-147">Como alternativa, para atribuir outra instância do TeamsUpgradePolicy que não tenha mode=TeamsOnly, você pode especificar o nome da instância desejada como o valor do parâmetro PolicyName no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ca295-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="ca295-148">Para ver uma lista de instâncias disponíveis do TeamsUpgradePolicy, execute Get-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ca295-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="ca295-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="ca295-149">See also</span></span>

[<span data-ttu-id="ca295-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ca295-150">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)