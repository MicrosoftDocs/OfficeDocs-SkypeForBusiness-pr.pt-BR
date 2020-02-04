---
title: 'Lync Server 2013: configurar a telefonia de um usuário'
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
ms.openlocfilehash: d57c4799c0fe9bb9dc698c3e0e74a9d73cbde524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="c29a6-102">Configurar a telefonia para um usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c29a6-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c29a6-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c29a6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c29a6-104">As configurações de telefonia são algumas das configurações individuais de uma conta de usuário que podem ser configuradas no painel de controle do Lync Server para o usuário (ou seja, se o usuário individual tiver sido habilitado para o Lync Server 2013 e a organização oferecer suporte a telefonia).</span><span class="sxs-lookup"><span data-stu-id="c29a6-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="c29a6-105">As opções de telefonia do usuário do Lync Server incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c29a6-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="c29a6-106">**Áudio/vídeo desabilitado**   o usuário não pode fazer chamadas com áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="c29a6-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="c29a6-107">**PC para PC somente**   o usuário pode fazer chamadas de áudio e vídeo de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="c29a6-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="c29a6-108">**Enterprise Voice**   o usuário pode usar a infraestrutura do Lync Server 2013 para direcionar todas as chamadas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="c29a6-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="c29a6-109">O usuário também pode fazer chamadas de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="c29a6-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="c29a6-110">**Controle de chamada remota**   o usuário pode usar o Lync Server 2013 para controlar o telefone de mesa e também pode fazer chamadas de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="c29a6-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="c29a6-111">Para obter detalhes sobre como configurar a telefonia de uma organização, consulte [Configurar a telefonia de um usuário no Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [implantação do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="c29a6-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="c29a6-112">Para configurar a telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="c29a6-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="c29a6-113">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c29a6-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c29a6-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c29a6-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c29a6-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c29a6-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c29a6-116">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c29a6-117">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="c29a6-118">Na tabela, clique na conta de usuário que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="c29a6-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="c29a6-119">No menu **Editar** , clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="c29a6-120">Em **telefonia**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c29a6-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="c29a6-121">Para desativar as chamadas de áudio e vídeo para o usuário, clique em **áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="c29a6-122">Para habilitar as comunicações de áudio PC para PC para o usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **PC para PC somente**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-122">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="c29a6-123">Especifique um valor para o **URI da linha** para o telefone que o usuário usa para comunicações de áudio PC para PC.</span><span class="sxs-lookup"><span data-stu-id="c29a6-123">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="c29a6-124">Para encaminhar as chamadas telefônicas do usuário usando a infraestrutura do Lync Server 2010 de acordo com a classe de política de serviço, incluindo comunicação de áudio PC para PC, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="c29a6-125">Em **URI da linha**, especifique o número de telefone do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c29a6-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="c29a6-126">Em **política de plano de discagem** e **política de voz**, especifique as políticas adequadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c29a6-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="c29a6-127">Para especificar as regras de normalização para a tradução de números de telefone discados pelo usuário para o formato E. 164, selecione o perfil de localização apropriado na **política de localização**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="c29a6-128">Para habilitar o controle de chamada remota, que permite que os usuários controlem a linha de telefone da área de trabalho do Lync Server 2013 para fazer chamadas de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="c29a6-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="c29a6-129">Em **URI de linha**, especifique o número de telefone para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="c29a6-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="c29a6-130">O usuário deve ter uma conexão de telefone de mesa e PBX (Private Branch Exchange) para roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c29a6-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c29a6-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="c29a6-131">See Also</span></span>


[<span data-ttu-id="c29a6-132">Modificando Propriedades de conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c29a6-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

