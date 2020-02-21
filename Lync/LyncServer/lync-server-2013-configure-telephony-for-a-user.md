---
title: 'Lync Server 2013: configurar telefonia para um usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fe22d70f442eed0cda1bbf56e79fb0e0e21f8a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="3518c-102">Configurar telefonia para um usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3518c-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3518c-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3518c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3518c-104">As configurações de telefonia são algumas das configurações individuais de uma conta de usuário que podem ser configuradas no painel de controle do Lync Server para o usuário (ou seja, se o usuário individual tiver sido habilitado para o Lync Server 2013 e a organização oferecer suporte à telefonia).</span><span class="sxs-lookup"><span data-stu-id="3518c-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="3518c-105">As opções de telefonia do usuário do Lync Server incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3518c-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="3518c-106">**Áudio/vídeo desabilitado**   o usuário não pode fazer chamadas com áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="3518c-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="3518c-107">**Somente PC-PC**   o usuário pode fazer apenas chamadas de áudio e vídeo de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="3518c-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="3518c-108">**Enterprise Voice**   o usuário pode usar a infraestrutura do Lync Server 2013 para rotear todas as chamadas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="3518c-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="3518c-109">O usuário também pode fazer chamadas PC-PC.</span><span class="sxs-lookup"><span data-stu-id="3518c-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="3518c-110">**Controle de chamada remota**   o usuário pode usar o Lync Server 2013 para controlar o telefone de mesa e também pode fazer chamadas PC-PC.</span><span class="sxs-lookup"><span data-stu-id="3518c-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="3518c-111">Para obter detalhes sobre como configurar telefonia para uma organização, consulte [Configurar telefonia para um usuário no Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [implantando o Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3518c-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="3518c-112">Para configurar telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="3518c-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="3518c-113">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3518c-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3518c-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3518c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3518c-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3518c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3518c-116">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3518c-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3518c-117">Na caixa **Pesquisar usuários**, digite toda ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta que deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="3518c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="3518c-118">Na tabela, clique na conta de usuário que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="3518c-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="3518c-119">No menu **Editar**, clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="3518c-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="3518c-120">Em **Telefonia**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3518c-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="3518c-121">Para desabilitar as chamadas de áudio e vídeo do usuário, clique em   **Áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="3518c-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="3518c-p103">Para habilitar a comunicação de áudio PC-PC do usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **Somente PC-PC**. Especifique um valor para **URI da Linha** para o telefone que o usuário usa para comunicações de áudio PC-PC.</span><span class="sxs-lookup"><span data-stu-id="3518c-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="3518c-124">Para encaminhar as chamadas telefônicas do usuário usando a infraestrutura do Lync Server 2010 de acordo com a classe de política de serviço, incluindo a comunicação de áudio de PC para PC, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="3518c-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="3518c-125">Em   **URI da Linha**, especifique o número de telefone para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3518c-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="3518c-126">Em **Política de plano de discagem** e \*\*Política de Voz \*\*, especifique as políticas apropriadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="3518c-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="3518c-127">Para especificar as regras de normalização para conversão de números de telefone discados pelo usuário no formato E.164, selecione o perfil de local apropriado no em **Política de local**.</span><span class="sxs-lookup"><span data-stu-id="3518c-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="3518c-128">Para habilitar o controle de chamada remota, que permite que os usuários controlem a linha de telefone da área de trabalho do Lync Server 2013 para fazer chamadas PC-PC e chamadas de PC para telefone, clique em **controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="3518c-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="3518c-129">Em **URI da Linha**, especifique o número de telefone para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="3518c-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="3518c-130">O usuário deve ter um telefone de mesa e a conexão PBX (central privada de comutação telefônica) para roteamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="3518c-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3518c-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="3518c-131">See Also</span></span>


[<span data-ttu-id="3518c-132">Modificando Propriedades da conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3518c-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

