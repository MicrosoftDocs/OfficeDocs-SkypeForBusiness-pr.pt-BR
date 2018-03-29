---
title: Modificar uma política de PIN existente no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Resumo: Modificar uma política PIN existente no Skype para Business Server 2015.'
ms.openlocfilehash: bb9be5807da0e72dfbc59d2000af82b181bfc6d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="ffcb5-103">Modificar uma política de PIN existente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ffcb5-103">Modify an existing PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ffcb5-104">**Resumo:** Modificar uma política PIN existente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-104">**Summary:** Modify an existing PIN policy in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ffcb5-105">Você pode usar a guia **Política de PIN** para fornecer autenticação de (PIN) número de identificação pessoal para usuários que estão se conectando ao Skype for Business com telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="ffcb5-106">Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="ffcb5-107">Siga estas etapas para modificar uma política de PIN no nível de usuário ou local.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="ffcb5-108">Para modificar uma política de PIN existente</span><span class="sxs-lookup"><span data-stu-id="ffcb5-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="ffcb5-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="ffcb5-110">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ffcb5-111">Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="ffcb5-112">Na página **Política de PIN**, clique em uma política, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ffcb5-p102">Em **Editar Política de PIN**, em **Comprimento mínimo do PIN**, digite ou selecione o comprimento mínimo do PIN que você deseja permitir. O comprimento mínimo padrão é de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p102">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="ffcb5-p103">Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon**. Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p103">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="ffcb5-118">Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="ffcb5-p104">Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p104">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="ffcb5-122">Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="ffcb5-p105">Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p105">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="ffcb5-p106">Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p106">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ffcb5-128">Recomendamos que você não permita os padrões comuns.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="ffcb5-129">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-129">Click **Commit**.</span></span>
    

