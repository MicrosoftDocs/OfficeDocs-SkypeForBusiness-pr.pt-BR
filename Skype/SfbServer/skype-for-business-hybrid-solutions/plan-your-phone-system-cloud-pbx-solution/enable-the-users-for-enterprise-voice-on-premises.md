---
title: Habilite os usuários para o Enterprise Voice no local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para um usuário usar o sistema telefônico no Office 365 (nuvem PBX), você deve primeiro habilitá-los para o Enterprise Voice e atribuí-las um número de telefone. Você fazer isso usando sua implantação no local enquanto o usuário ainda é hospedado na implantação no local.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657444"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="56c56-104">Habilite os usuários para o Enterprise Voice no local</span><span class="sxs-lookup"><span data-stu-id="56c56-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="56c56-105">Para um usuário usar o sistema telefônico no Office 365 (nuvem PBX), você deve primeiro habilitá-los para o Enterprise Voice e atribuí-las um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="56c56-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="56c56-106">Você fazer isso usando sua implantação no local enquanto o usuário ainda é hospedado na implantação no local.</span><span class="sxs-lookup"><span data-stu-id="56c56-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="56c56-107">Para habilitar um usuário para o Enterprise Voice no local e atribuir um número de telefone</span><span class="sxs-lookup"><span data-stu-id="56c56-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="56c56-108">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="56c56-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="56c56-109">Utilize o menu Iniciar ou o atalho na área de trabalho para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56c56-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="56c56-110">Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56c56-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="56c56-111">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="56c56-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="56c56-112">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="56c56-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="56c56-113">Na tabela, clique no Skype para Business Online conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="56c56-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="56c56-114">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="56c56-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="56c56-115">Em **Telefonia**, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="56c56-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="56c56-p103">Clique em **URI da Linha**, digite um número de telefone único e normalizado (por exemplo, tel:+14255550200) e, em seguida, clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="56c56-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="56c56-118">Considerações especiais ao habilitar usuários para o Enterprise Voice no local</span><span class="sxs-lookup"><span data-stu-id="56c56-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="56c56-119">Em alguns casos, pode ser necessário modificar o modo de habilitar usuários para o Enterprise Voice para garantir que eles consigam fazer e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="56c56-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="56c56-120">Se você tiver usuários em sua implantação que atendem às seguintes condições, execute as etapas foram incluídas para permitir que o usuário para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="56c56-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="56c56-121">Se um usuário é criado no seu local AD e sincronizadas com Skype para Business Online sem sendo habilitados para o Skype para negócios ou para o Enterprise Voice e não tem um LineURI definido, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores em < C0 > <b1></b1> com valores reais para seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="56c56-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="56c56-122">Se um usuário já estiver habilitado para Skype para negócios localmente, mas não foi habilitado para Enterprise Voice ou atribuído um LineURI antes que está sendo movido para Skype para Business Online, execute o seguinte cmdlet para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="56c56-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="56c56-123">Se um usuário é já está habilitado no Skype for Business no local, mas não habilitado para o Enterprise Voice, mesmo se já atribuído um LineURI, execute o seguinte cmdlet para cada usuário afetado:</span><span class="sxs-lookup"><span data-stu-id="56c56-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


