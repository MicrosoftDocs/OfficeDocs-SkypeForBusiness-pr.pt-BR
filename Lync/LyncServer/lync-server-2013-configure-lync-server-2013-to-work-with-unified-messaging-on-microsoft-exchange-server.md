---
title: 'Lync Server 2013: Configurar o Lync Server 2013 para trabalhar com a Unificação de Mensagens no Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="be13d-102">Configurar o Lync Server 2013 para trabalhar com a Unificação de Mensagens no Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="be13d-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="be13d-103">_**Tópico da última modificação:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="be13d-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="be13d-104">Esta etapa requer o utilitário de integração do Exchange UM (OcsUmUtil. exe).</span><span class="sxs-lookup"><span data-stu-id="be13d-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="be13d-105">Esta ferramenta está localizada no servidor do Lync Server 2013 em.. \\Arquivos de\\programas arquivos\\comuns Microsoft Lync Server\\2013 support Folder.</span><span class="sxs-lookup"><span data-stu-id="be13d-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="be13d-106">Executando o utilitário de integração de UM Exchange</span><span class="sxs-lookup"><span data-stu-id="be13d-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="be13d-107">O utilitário de integração do Exchange UM deve ser executado a partir de uma conta de usuário com as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="be13d-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="be13d-108">Associação nos grupos RTCUniversalServerAdmins e RtcUniversalUserAdmins (que inclui a permissão para ler as configurações de mensagens unificadas do Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="be13d-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="be13d-109">Direitos de usuário no domínio para criar objetos de contato no contêiner de unidade organizacional (OU) especificado.</span><span class="sxs-lookup"><span data-stu-id="be13d-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="be13d-110">Quando você executa o utilitário de integração do Exchange UM, ele executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="be13d-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="be13d-111">Cria objetos de contato para cada número de atendente e acesso do assinante a ser usado por usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="be13d-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="be13d-112">Verifica se o nome de cada plano de discagem de voz empresarial corresponde ao seu próprio contexto de telefone de plano de discagem de mensagens unificadas (UM).</span><span class="sxs-lookup"><span data-stu-id="be13d-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="be13d-113">Essa correspondência só será necessária se o plano de discagem do UM estiver sendo executado em uma versão do Exchange *anterior* ao Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="be13d-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be13d-114">Antes de executar o utilitário de integração do Exchange UM, certifique-se de ter feito o seguinte:</span><span class="sxs-lookup"><span data-stu-id="be13d-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="be13d-115">Crie um ou mais planos de discagem de UM do Exchange, conforme descrito na documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="be13d-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="be13d-116">Para o Microsoft Exchange Server 2010, &quot;consulte criar um plano&quot; de discagem de um em. <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a></span><span class="sxs-lookup"><span data-stu-id="be13d-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="be13d-117">Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot;como criar um plano&quot; de DISCAgem de URI SIP de <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>Unificação de mensagens em.</span><span class="sxs-lookup"><span data-stu-id="be13d-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="be13d-118">Crie um ou mais planos de discagem do Lync Server correspondentes, conforme descrito em <a href="lync-server-2013-create-a-dial-plan.md">criar um plano de discagem no Lync server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="be13d-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="be13d-119">Se estiver usando uma versão do Exchange anterior ao Microsoft Exchange Server 2010 SP1, você deve digitar o nome de domínio totalmente qualificado (FQDN) do plano de discagem SIP do Exchange Unified Messaging (UM) correspondente no campo <STRONG>nome simples</STRONG> do plano de discagem do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be13d-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="be13d-120">Se você estiver usando o Microsoft Exchange Server 2010 SP1 ou Service Pack mais recente, o nome do plano de discagem correspondente não será necessário.</span><span class="sxs-lookup"><span data-stu-id="be13d-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="be13d-121">Crie um atendedor automático e certifique-se de que o número de acesso do assinante e o número do auto Attendant estejam no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="be13d-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="be13d-122">Para executar o utilitário de integração de UM Exchange</span><span class="sxs-lookup"><span data-stu-id="be13d-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="be13d-123">Em um servidor front-end, abra um prompt de comando e digite **CD%\\COMMONPROGRAMFILES% Microsoft Lync\\Server 2013 support**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="be13d-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="be13d-124">Digite **OcsUmUtil. exe**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="be13d-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="be13d-125">Clique em **carregar dados** para localizar todas as florestas do Exchange confiáveis.</span><span class="sxs-lookup"><span data-stu-id="be13d-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="be13d-126">Na lista **planos de discagem SIP** , selecione um plano de discagem do um SIP para o qual você deseja criar objetos de contato e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="be13d-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="be13d-127">Na caixa de **contato** , aceite a unidade organizacional padrão ou clique em **procurar** para iniciar o **seletor de ou**.</span><span class="sxs-lookup"><span data-stu-id="be13d-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="be13d-128">Na caixa do **seletor de ou** , você pode selecionar uma UO e clicar em **OK**, ou pode clicar em **fazer nova UO** para criar uma nova unidade organizacional na raiz ou em qualquer outra UO do domínio (por exemplo, "ou = contas especiais do RTC, DC = fourthcoffee, DC = com") e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="be13d-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be13d-129">O nome diferenciado (DN) da OU que você selecionou ou criou agora é exibido na caixa <STRONG>unidade organizacional</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="be13d-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="be13d-130">Na caixa **nome** , aceite o nome do plano de discagem padrão ou digite um novo nome para exibição para o objeto de contato que você está criando.</span><span class="sxs-lookup"><span data-stu-id="be13d-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be13d-131">Por exemplo, se você estiver criando um objeto de contato do acesso ao Assinante, você pode simplesmente nomeá-lo como assinante.</span><span class="sxs-lookup"><span data-stu-id="be13d-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="be13d-132">Na caixa **endereço SIP** , aceite o endereço SIP padrão ou digite um novo endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="be13d-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be13d-133">Se você digitar um novo endereço SIP, ele deve começar com <STRONG>SIP:</STRONG> (isto é, "SIP:" incluindo os dois-pontos).</span><span class="sxs-lookup"><span data-stu-id="be13d-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="be13d-134">Na lista **servidor ou pool** , selecione o servidor Standard Edition ou o pool de front-end no qual o objeto de contato deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="be13d-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be13d-135">Preferencialmente, o pool selecionado é o mesmo pool em que os usuários habilitados para o Enterprise Voice e o Exchange UM são implantados.</span><span class="sxs-lookup"><span data-stu-id="be13d-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="be13d-136">Na lista **número de telefone** , selecione **Inserir número de telefone** ou **Use este número piloto no Exchange um** e, em seguida, digite um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="be13d-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="be13d-137">Na lista **tipo de contato** , selecione o tipo de contato que você deseja criar e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="be13d-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="be13d-138">Repita as etapas de 1 a 10 para objetos de contato adicionais que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="be13d-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be13d-139">Você deve criar pelo menos um contato para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="be13d-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="be13d-140">Se você quiser acesso externo, também precisará de um contato do acesso do assinante e especificar números do Direct Inward Dial (DID).</span><span class="sxs-lookup"><span data-stu-id="be13d-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="be13d-141">Para verificar se os objetos de contato foram criados, abra usuários e computadores do Active Directory e selecione a OU em que os objetos foram criados.</span><span class="sxs-lookup"><span data-stu-id="be13d-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="be13d-142">Os objetos de contato devem aparecer no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="be13d-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="be13d-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="be13d-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

