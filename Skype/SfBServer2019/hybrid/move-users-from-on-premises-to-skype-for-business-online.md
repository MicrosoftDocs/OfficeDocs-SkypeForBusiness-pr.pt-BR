---
title: Mover usuários do local para o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Saiba como mover usuários para Skype para negócios Online.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243994"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="8d3d5-103">Mover usuários do local para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8d3d5-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="8d3d5-104">Depois de mover um usuário no local para Skype para Business Online, o usuário interage com Skype para Business Online para sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="8d3d5-105">Todos os contatos que existiam no local estarão disponíveis na Skype para Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro são atualizadas para para que os links apontam para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="8d3d5-106">Se o usuário estiver habilitado para conferência de áudio, as reuniões também incluirá as coordenadas de discagem.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="8d3d5-107">Para mover usuários de um ambiente local para Skype para Business Online, use o cmdlet Move-CsUser ou o Skype para painel de controle do Business Server, ambos os quais são as ferramentas de local.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="8d3d5-108">Antes de mover todos os usuários, certifique-se de revisar os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="8d3d5-109">Mover os usuários com Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="8d3d5-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="8d3d5-110">Move-CsUser está disponível no Skype local para a janela do PowerShell de Shell de gerenciamento de negócios.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="8d3d5-111">Você deve ter privilégios suficientes em ambos o ambiente local, bem como o locatário do Office 365, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="8d3d5-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="8d3d5-112">Você pode usar uma única conta que possua privilégios nos dois ambientes, ou você pode iniciar uma Skype no local para a janela do Shell de gerenciamento do servidor de negócios com credenciais no local e usar o `-Credential` parâmetro para especificar as credenciais para um Office 365 conta com a função administrativa do Office 365 necessária.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="8d3d5-113">Para mover um usuário para online usando o Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="8d3d5-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="8d3d5-114">Especifique o usuário mover usando o parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="8d3d5-115">Especificar o - parâmetro de destino com o valor "sipfed.online.lync. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="8d3d5-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="8d3d5-116">Se você não tiver uma conta com permissões suficientes em ambos no local e o Office 365, use o parâmetro - credential para fornecer uma conta com permissões suficientes no Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="8d3d5-117">Se a conta com permissões no Office 365 não termina em "on.microsoft. <span>com ", e em seguida, você deve especificar o parâmetro - HostedMigrationOverrideUrl, com o valor correto, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="8d3d5-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="8d3d5-118">A seguinte sequência de cmdlet pode ser usada para mover um usuário para Skype para Business Online e assume a credencial do Office 365 é uma conta separada e fornecidos como entrada para o prompt de Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="8d3d5-119">Mover os usuários com Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="8d3d5-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="8d3d5-120">Abra o Skype para controle de servidor de negócios app do painel.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="8d3d5-121">No painel de navegação esquerdo, escolha **usuários**.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="8d3d5-122">Use o comando **Localizar** para localizar o (s) que você deseja mover para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="8d3d5-123">Selecione o (s) e, no menu suspenso de **ação** acima da lista, selecione **mover usuários selecionados para Skype para negócios Online**.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="8d3d5-124">No assistente, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="8d3d5-125">Se solicitado, faça logon no Office 365, com uma conta que termina em. onmicrosoft.com e tem permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="8d3d5-126">Clique em **Avançar**e, em seguida, **Avançar** mais uma vez para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="8d3d5-127">Observe que as mensagens de status sobre o sucesso ou falha são fornecidas na parte superior do aplicativo principal do painel de controle, não no assistente.</span><span class="sxs-lookup"><span data-stu-id="8d3d5-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d3d5-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8d3d5-128">See also</span></span>

[<span data-ttu-id="8d3d5-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="8d3d5-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)