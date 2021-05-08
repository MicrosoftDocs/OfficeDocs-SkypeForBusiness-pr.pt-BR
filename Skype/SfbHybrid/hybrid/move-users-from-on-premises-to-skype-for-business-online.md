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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237957"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="99596-103">Mover usuários do ambiente local para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="99596-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="99596-104">Depois de mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business Online para sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="99596-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="99596-105">Todos os contatos existentes no local estarão disponíveis no Skype for Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro serão atualizadas para que os links apontem para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="99596-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="99596-106">Se o usuário estiver habilitado para Audioconferência, as reuniões também incluirão coordenadas discada.</span><span class="sxs-lookup"><span data-stu-id="99596-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="99596-107">Para mover usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o painel de controle Skype for Business Server, ambos são ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="99596-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="99596-108">Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="99596-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="99596-109">Mover usuários com Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="99596-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="99596-110">Move-CsUser está disponível em uma janela local Skype for Business Shell de Gerenciamento do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99596-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="99596-111">Você deve ter privilégios suficientes no ambiente local, bem como na organização Microsoft 365/Office 365, conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="99596-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="99596-112">Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta Microsoft 365 ou Office 365 com a função administrativa `-Credential` necessária.</span><span class="sxs-lookup"><span data-stu-id="99596-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="99596-113">Para mover um usuário para online usando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="99596-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="99596-114">Especifique o usuário para mover usando o parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="99596-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="99596-115">Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="99596-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="99596-116">Se você não tiver uma conta com permissões suficientes no local e Office 365, use o parâmetro -credential para fornecer uma conta com permissões suficientes Office 365.</span><span class="sxs-lookup"><span data-stu-id="99596-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="99596-117">Se a conta com permissões no Office 365 não terminar em ".onmicrosoft. <span> com", em seguida, você deve especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="99596-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="99596-118">A sequência de cmdlets a seguir pode ser usada para mover um usuário para Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="99596-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="99596-119">Ele supõe que a credencial Microsoft 365 ou Office 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="99596-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="99596-120">Se a conta de administrador estiver habilitada para MFA (Autenticação Multifa factor), não especifique o parâmetro -Credential.</span><span class="sxs-lookup"><span data-stu-id="99596-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="99596-121">O administrador será solicitado a solicitar credenciais.</span><span class="sxs-lookup"><span data-stu-id="99596-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="99596-122">Mover usuários com Skype for Business Server Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="99596-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="99596-123">Abra o aplicativo Skype for Business Server Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="99596-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="99596-124">Na navegação à esquerda, escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="99596-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="99596-125">Use **Localizar** para localizar os usuários que você gostaria de mover para Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="99596-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="99596-126">Selecione o(s) usuário(s) e, em seguida, no menu suspenso **Ação** acima da lista, escolha Mover usuários selecionados para Skype for Business **Online**.</span><span class="sxs-lookup"><span data-stu-id="99596-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="99596-127">No assistente, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="99596-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="99596-128">Se solicitado, entre no Microsoft 365 ou Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="99596-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="99596-129">Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="99596-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="99596-130">Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.</span><span class="sxs-lookup"><span data-stu-id="99596-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="99596-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="99596-131">See also</span></span>

[<span data-ttu-id="99596-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="99596-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)