---
title: 'Lync Server 2013: configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server'
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
ms.openlocfilehash: b297a505b1a12335e545895e0203ffc0e29c7354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507628"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="659b4-102">Configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="659b4-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="659b4-103">_**Última modificação do tópico:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="659b4-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="659b4-104">Esta etapa requer o Utilitário de Integração do UM do Exchange (OcsUmUtil.exe).</span><span class="sxs-lookup"><span data-stu-id="659b4-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="659b4-105">Essa ferramenta está localizada no servidor do Lync Server 2013 no.. \\ Arquivos de programa \\ Arquivos comuns \\ do Microsoft Lync Server 2013 \\ support Folder.</span><span class="sxs-lookup"><span data-stu-id="659b4-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="659b4-106">Executando o Utilitário de Integração do UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="659b4-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="659b4-107">O Utilitário de Integração do UM do Exchange deve ser executado em uma conta de usuário com as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="659b4-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="659b4-108">Associação nos grupos RTCUniversalServerAdmins e RtcUniversalUserAdmins (que inclui a permissão para ler as configurações da Unificação de Mensagens do Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="659b4-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="659b4-109">Direitos de usuário no domínio para criar objetos de contato no contêiner de unidade organizacional (OU) especificado.</span><span class="sxs-lookup"><span data-stu-id="659b4-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="659b4-110">Quando você executa o Utilitário de Integração do UM do Exchange, ele realiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="659b4-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="659b4-111">Cria objetos de contato para cada número de telefone do assinante e de atendedor automático a ser utilizado pelos usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="659b4-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="659b4-112">Verifica se o nome de cada plano de discagem do Enterprise Voice corresponde ao seu contexto de telefone do plano de discagem de Unificação de mensagens (UM) correspondente.</span><span class="sxs-lookup"><span data-stu-id="659b4-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="659b4-113">Essa correspondência será necessária somente se o plano de discagem da UM estiver sendo executado em uma versão do Exchange *anterior* ao Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="659b4-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="659b4-114">Antes de executar o utilitário de integração do UM do Exchange, certifique-se de ter feito o seguinte:</span><span class="sxs-lookup"><span data-stu-id="659b4-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="659b4-115">Crie um ou mais planos de discagem de UM do Exchange, conforme descrito na documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="659b4-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="659b4-116">Para o Microsoft Exchange Server 2010, consulte &quot; criar um plano de discagem de um &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> .</span><span class="sxs-lookup"><span data-stu-id="659b4-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="659b4-117">Para o Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot; como criar um plano de discagem URI SIP de Unificação &quot; de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> .</span><span class="sxs-lookup"><span data-stu-id="659b4-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="659b4-118">Crie um ou mais planos de discagem do Lync Server correspondentes, conforme descrito em <a href="lync-server-2013-create-a-dial-plan.md">Create a dial Plan in Lync server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="659b4-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="659b4-119">Se você estiver usando uma versão do Exchange anterior ao Microsoft Exchange Server 2010 SP1, deverá digitar o nome de domínio totalmente qualificado (FQDN) do plano de discagem SIP da Unificação de mensagens (UM) correspondente do Exchange no campo <STRONG>nome simples</STRONG> do plano de discagem do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="659b4-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="659b4-120">Se você estiver usando o Microsoft Exchange Server 2010 SP1 ou o Service Pack mais recente, o nome do plano de discagem correspondente não será necessário.</span><span class="sxs-lookup"><span data-stu-id="659b4-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="659b4-121">Crie um atendedor automático e certifique-se que o número de acesso do assinante e o número do atendedor automático estejam no formato E.164.</span><span class="sxs-lookup"><span data-stu-id="659b4-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="659b4-122">Para executar o Utilitário de Integração do UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="659b4-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="659b4-123">Em um servidor front-end, abra um prompt de comando e digite **CD% COMMONPROGRAMFILES% \\ Microsoft Lync Server 2013 \\ support**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="659b4-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="659b4-124">Digite **OcsUmUtil.exe** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="659b4-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="659b4-125">Clique em **Carregar Dados** para localizar todas as florestas confiáveis do Exchange.</span><span class="sxs-lookup"><span data-stu-id="659b4-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="659b4-126">Na lista **Planos de Discagem SIP**, selecione o plano de discagem SIP do UM para o qual você deseja criar objetos de contato e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="659b4-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="659b4-p104">Na caixa **Contato**, aceite a unidade organizacional padrão ou clique em **Procurar** para iniciar o **Seletor de UO**. Na caixa **Seletor de UO**, você pode selecionar uma UO e clicar em **OK**, ou pode clicar em **Criar Nova UO** para criar uma nova unidade organizacional na raiz ou em qualquer outra UO do domínio (por exemplo, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"); em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="659b4-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="659b4-129">O nome diferenciado (DN) da UO selecionada ou criada será agora exibido na caixa <STRONG>Unidade Organizacional</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="659b4-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="659b4-130">Na caixa **Nome**, aceite o nome padrão do plano de discagem ou digite um novo nome de exibição para o objeto de contato que você está criando.</span><span class="sxs-lookup"><span data-stu-id="659b4-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="659b4-131">Por exemplo, se estiver criando um objeto de contato de acesso do assinante, bastará nomeá-lo como Acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="659b4-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="659b4-132">Na caixa **Endereço SIP**, aceite o endereço SIP padrão ou digite um novo endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="659b4-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="659b4-133">Se você digitar um novo endereço SIP, ele deve começar com <STRONG>SIP:</STRONG> (isto é, "SIP:" incluindo os dois pontos).</span><span class="sxs-lookup"><span data-stu-id="659b4-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="659b4-134">Na lista **servidor ou pool** , selecione o servidor Standard Edition ou o pool de front-ends no qual o objeto de contato deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="659b4-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="659b4-135">De preferência, o pool selecionado deverá ser o mesmo no qual os usuários habilitados para o Enterprise Voice e o UM do Exchange estão implantados.</span><span class="sxs-lookup"><span data-stu-id="659b4-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="659b4-136">Na lista **Número de Telefone**, selecione **Insira o número de telefone** ou **Usar este número piloto do UM do Exchange** e digite um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="659b4-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="659b4-137">Na lista **Tipo de Contato**, selecione o tipo de contato que deseja criar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="659b4-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="659b4-138">Repita as etapas de 1 a 10 para outros objetos de contato que você deseje criar.</span><span class="sxs-lookup"><span data-stu-id="659b4-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="659b4-p105">Você deve criar pelo menos um contato para cada atendedor automático. Se desejar acesso externo, você também precisará de um contato Acesso do Assinante e terá que especificar números DID (discagem direta interna).</span><span class="sxs-lookup"><span data-stu-id="659b4-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="659b4-p106">Para verificar se os objetos de contato foram criados, abra Usuários e Computadores do Active Directory e selecione a UO na qual os objetos foram criados. Os objetos de contato devem aparecer no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="659b4-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="659b4-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="659b4-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

