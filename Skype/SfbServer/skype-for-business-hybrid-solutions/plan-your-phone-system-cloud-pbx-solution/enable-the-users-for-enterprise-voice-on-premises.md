---
title: Habilitar os usuários para o Enterprise Voice local
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que um usuário use o Sistema de Telefonia (Cloud PBX), você deve primeiro habilita-lo para o Enterprise Voice e atribuir um número de telefone a ele. Faça isso usando sua implantação local enquanto o usuário ainda estiver na implantação local.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359187"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="4a903-104">Habilitar os usuários para o Enterprise Voice local</span><span class="sxs-lookup"><span data-stu-id="4a903-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="4a903-105">Para que um usuário use o Sistema de Telefonia (Cloud PBX), você deve primeiro habilita-lo para o Enterprise Voice e atribuir um número de telefone a ele.</span><span class="sxs-lookup"><span data-stu-id="4a903-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="4a903-106">Faça isso usando sua implantação local enquanto o usuário ainda estiver na implantação local.</span><span class="sxs-lookup"><span data-stu-id="4a903-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="4a903-107">O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.</span><span class="sxs-lookup"><span data-stu-id="4a903-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="4a903-108">Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.</span><span class="sxs-lookup"><span data-stu-id="4a903-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="4a903-109">Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="4a903-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="4a903-110">Para habilitar um usuário para o Enterprise Voice local e atribuir um número de telefone</span><span class="sxs-lookup"><span data-stu-id="4a903-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="4a903-111">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4a903-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4a903-112">Use o menu Iniciar ou o atalho da área de trabalho para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a903-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="4a903-113">Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a903-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4a903-114">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="4a903-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4a903-115">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="4a903-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4a903-116">Na tabela, clique na conta de usuário do Skype for Business Online que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4a903-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="4a903-117">No menu **Editar,** clique em **Mostrar Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="4a903-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="4a903-118">Em **Telefonia,** clique **em Enterprise Voice.**</span><span class="sxs-lookup"><span data-stu-id="4a903-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="4a903-119">Clique **em URI** da Linha e digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="4a903-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="4a903-120">Em seguida, **clique em Commit**.</span><span class="sxs-lookup"><span data-stu-id="4a903-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="4a903-121">Considerações especiais durante a habilitação de usuários para o Enterprise Voice no local</span><span class="sxs-lookup"><span data-stu-id="4a903-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="4a903-122">Em alguns casos, talvez seja necessário modificar a maneira como você habilita os usuários para o Enterprise Voice para garantir que eles possam fazer e receber chamadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="4a903-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="4a903-123">Se você tiver usuários em sua implantação que atendem às seguintes condições, execute as etapas incluídas para habilitar o usuário para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4a903-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="4a903-124">Se um usuário for criado em seu AD local e depois sincronizado com o Skype for Business Online sem estar habilitado para o Skype for Business ou para o Enterprise Voice e não tiver um conjunto lineURI, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores por valores reais para seu \< \> ambiente:</span><span class="sxs-lookup"><span data-stu-id="4a903-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="4a903-125">Se um usuário já estiver habilitado para o Skype for Business no local, mas não tiver sido habilitado para o Enterprise Voice ou atribuído a um LineURI antes de ser movido para o Skype for Business Online, execute o seguinte cmdlet para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="4a903-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="4a903-126">Se um usuário já estiver habilitado no Skype for Business local, mas não estiver habilitado para o Enterprise Voice, mesmo se já tiver atribuído um LineURI, execute o seguinte cmdlet para cada usuário afetado:</span><span class="sxs-lookup"><span data-stu-id="4a903-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


