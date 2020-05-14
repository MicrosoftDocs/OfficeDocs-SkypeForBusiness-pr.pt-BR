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
description: Saiba como mover usuários para o Skype for Business online.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221111"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="80506-103">Mover usuários do ambiente local para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80506-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="80506-104">Após mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business online por sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="80506-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="80506-105">Todos os contatos que existiam no local estarão disponíveis no Skype for Business Online, e todas as reuniões existentes que o usuário organizou para o futuro serão atualizadas para que eles apontem para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="80506-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="80506-106">Se o usuário estiver habilitado para audioconferência, as reuniões também incluirão as coordenadas de discagem.</span><span class="sxs-lookup"><span data-stu-id="80506-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="80506-107">Para mover os usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o painel de controle do Skype for Business Server, ambos são ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="80506-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="80506-108">Antes de mover qualquer usuário, leia os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="80506-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="80506-109">Mover usuários com o move-CsUser</span><span class="sxs-lookup"><span data-stu-id="80506-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="80506-110">O move-CsUser está disponível em uma janela do PowerShell do Shell de gerenciamento do Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="80506-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="80506-111">Você deve ter privilégios suficientes no ambiente local, bem como na organização do Microsoft 365/Office 365, conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="80506-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="80506-112">Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de gerenciamento do Skype for Business Server com credenciais locais e usar o `-Credential` parâmetro para especificar credenciais para uma conta do Microsoft 365 ou do Office 365 com a função administrativa necessária.</span><span class="sxs-lookup"><span data-stu-id="80506-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="80506-113">Para mover um usuário para o modo online usando o move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="80506-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="80506-114">Especifique o usuário a ser movido usando o parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="80506-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="80506-115">Especifique o parâmetro-Target com o valor "sipfed. online. Lync. <span> com ".</span><span class="sxs-lookup"><span data-stu-id="80506-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="80506-116">Se você não tiver uma conta com permissões suficientes no local e no Office 365, use o parâmetro-Credential para fornecer uma conta com permissões suficientes no Office 365.</span><span class="sxs-lookup"><span data-stu-id="80506-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="80506-117">Se a conta com permissões no Office 365 não termina em ". onmicrosoft. <span> com ", em seguida, você deve especificar o parâmetro-HostedMigrationOverrideUrl com o valor correto, conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="80506-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="80506-118">A sequência de cmdlet a seguir pode ser usada para mover um usuário para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="80506-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="80506-119">Ele pressupõe que a credencial do Microsoft 365 ou do Office 365 seja uma conta separada e fornecida como entrada para o prompt Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="80506-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="80506-120">Se a conta de administrador for a MFA (autenticação multifator) habilitada, não especifique o parâmetro-Credential.</span><span class="sxs-lookup"><span data-stu-id="80506-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="80506-121">As credenciais do administrador serão solicitadas.</span><span class="sxs-lookup"><span data-stu-id="80506-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="80506-122">Mover usuários com o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80506-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="80506-123">Abra o aplicativo painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80506-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="80506-124">Na navegação à esquerda, escolha **usuários**.</span><span class="sxs-lookup"><span data-stu-id="80506-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="80506-125">Use **Localizar** para localizar os usuários que você gostaria de mudar para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="80506-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="80506-126">Selecione o (s) usuário (s) e, no menu suspenso **ação** acima da lista, escolha **mover usuários selecionados para o Skype for Business online**.</span><span class="sxs-lookup"><span data-stu-id="80506-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="80506-127">No assistente, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="80506-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="80506-128">Se solicitado, entre no Microsoft 365 ou no Office 365 com uma conta que termine no. onmicrosoft.com e tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="80506-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="80506-129">Clique em **Avançar**e, em seguida, **mais uma vez** para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="80506-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="80506-130">Observe que as mensagens de status referentes a sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, e não no assistente.</span><span class="sxs-lookup"><span data-stu-id="80506-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="80506-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="80506-131">See also</span></span>

[<span data-ttu-id="80506-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="80506-132">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
