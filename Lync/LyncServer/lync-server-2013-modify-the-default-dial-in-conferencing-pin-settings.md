---
title: 'Lync Server 2013: modificar as configurações de PIN de conferência discada padrão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa34bf6320a290dc774971699ca6f99d05dc2b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515258"
---
# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a><span data-ttu-id="823c2-102">Modificar as configurações de PIN de conferência discada padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="823c2-102">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="823c2-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="823c2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="823c2-104">A política de PIN global define as regras para PINs de conferências de discagem no nível da floresta.</span><span class="sxs-lookup"><span data-stu-id="823c2-104">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="823c2-105">Execute estas etapas para modificar a política de PIN de conferência de discagem global.</span><span class="sxs-lookup"><span data-stu-id="823c2-105">Follow these steps to modify the global dial-in conferencing PIN policy.</span></span> <span data-ttu-id="823c2-106">Para obter detalhes sobre como criar ou modificar uma política de PIN de conferência discada no nível do site ou usuário, confira [criar ou modificar as configurações de PIN de conferência discada no Lync Server 2013 para um site ou grupo de usuários](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="823c2-106">For details about creating or modifying a dial-in conferencing PIN policy at the site or user level, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

<div>

## <a name="to-modify-the-global-pin-policy"></a><span data-ttu-id="823c2-107">Para modificar a política PIN global</span><span class="sxs-lookup"><span data-stu-id="823c2-107">To modify the global PIN policy</span></span>

1.  <span data-ttu-id="823c2-108">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="823c2-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="823c2-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="823c2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="823c2-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="823c2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="823c2-111">Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="823c2-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="823c2-112">Na página **Política de PIN**, clique na política **Global**, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="823c2-112">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="823c2-p103">Em**Editar Política de PIN**, em **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="823c2-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="823c2-p104">Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon** . Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="823c2-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="823c2-118">Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="823c2-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="823c2-p105">Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="823c2-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="823c2-122">Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.</span><span class="sxs-lookup"><span data-stu-id="823c2-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="823c2-p106">Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.</span><span class="sxs-lookup"><span data-stu-id="823c2-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="823c2-p107">Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.</span><span class="sxs-lookup"><span data-stu-id="823c2-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="823c2-128">Recomendamos que você não permita os padrões comuns.</span><span class="sxs-lookup"><span data-stu-id="823c2-128">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="823c2-129">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="823c2-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

