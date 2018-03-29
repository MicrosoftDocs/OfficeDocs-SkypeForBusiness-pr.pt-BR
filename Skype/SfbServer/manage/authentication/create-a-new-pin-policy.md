---
title: Criar uma nova política de PIN no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Resumo: Crie uma nova política PIN no Skype para Business Server 2015.'
ms.openlocfilehash: d04c19f09830b971300d2ff9bf4a8a1d93994f7c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="4af0a-103">Criar uma nova política de PIN no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4af0a-103">Create a new PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4af0a-104">**Resumo:** Crie uma nova política PIN no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4af0a-104">**Summary:** Create a new PIN policy in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4af0a-105">Você pode usar a página **Política** de PIN para fornecer autenticação de (PIN) número de identificação pessoal para usuários que estão se conectando ao Skype for Business com telefones IP.</span><span class="sxs-lookup"><span data-stu-id="4af0a-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="4af0a-106">Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.</span><span class="sxs-lookup"><span data-stu-id="4af0a-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="4af0a-107">Siga estas etapas para criar uma política de PIN de nível de usuário ou de nível de site.</span><span class="sxs-lookup"><span data-stu-id="4af0a-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="4af0a-108">Para criar uma política de PIN de site ou usuário</span><span class="sxs-lookup"><span data-stu-id="4af0a-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="4af0a-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4af0a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="4af0a-110">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="4af0a-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4af0a-111">Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="4af0a-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="4af0a-112">Na página **Política de PIN**, clique em **Novo** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4af0a-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="4af0a-p102">Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de PIN**, em **Nome**, digite um nome que descreve a política.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="4af0a-p103">Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4af0a-118">No campo **Descrição**, digite uma descrição da política de PIN.</span><span class="sxs-lookup"><span data-stu-id="4af0a-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="4af0a-p104">No campo **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="4af0a-p105">Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon**. Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="4af0a-124">Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="4af0a-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="4af0a-p106">Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="4af0a-128">Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.</span><span class="sxs-lookup"><span data-stu-id="4af0a-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="4af0a-p107">Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="4af0a-p108">Para permitir padrões comuns de dígitos nos PINs, como "1234" e "8888", marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.</span><span class="sxs-lookup"><span data-stu-id="4af0a-p108">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4af0a-134">Recomendamos que você não permita os padrões comuns.</span><span class="sxs-lookup"><span data-stu-id="4af0a-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="4af0a-135">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4af0a-135">Click **Commit**.</span></span>
    

