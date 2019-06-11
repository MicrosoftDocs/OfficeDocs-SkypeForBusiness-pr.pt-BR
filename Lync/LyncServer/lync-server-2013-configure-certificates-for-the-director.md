---
title: 'Lync Server 2013: Configurar certificados do Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="5afde-102">Configurar certificados do Diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5afde-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5afde-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5afde-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5afde-104">Ao executar o assistente de certificado, certifique-se de que você esteja conectado usando uma conta que seja membro de um grupo que tenha recebido as permissões apropriadas para o tipo de modelo de certificado que você vai usar.</span><span class="sxs-lookup"><span data-stu-id="5afde-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="5afde-105">Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="5afde-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="5afde-106">Se você usar uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões de Registro necessárias para usar esse modelo.</span><span class="sxs-lookup"><span data-stu-id="5afde-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="5afde-107">Cada diretor requer um certificado padrão, um certificado interno da Web e um certificado externo da Web.</span><span class="sxs-lookup"><span data-stu-id="5afde-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="5afde-108">Para obter detalhes sobre os requisitos de certificado para os directors, consulte [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5afde-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="5afde-109">Use o procedimento a seguir para configurar certificados de director.</span><span class="sxs-lookup"><span data-stu-id="5afde-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="5afde-110">Repita o procedimento para cada diretor.</span><span class="sxs-lookup"><span data-stu-id="5afde-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="5afde-111">As etapas deste procedimento descrevem como configurar um certificado de uma CA (autoridade de certificação) raiz corporativa interna implantada pela sua organização e com o processamento de solicitação offline.</span><span class="sxs-lookup"><span data-stu-id="5afde-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="5afde-112">Para obter detalhes sobre como obter certificados de uma autoridade de certificação externa, entre em contato com a equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="5afde-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="5afde-113">Para configurar certificados para o diretor ou o pool do diretor</span><span class="sxs-lookup"><span data-stu-id="5afde-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="5afde-114">No assistente de implantação do Lync Server, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="5afde-115">Na página **Assistente de Certificados**, clique em **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="5afde-116">Na página **solicitação de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="5afde-117">Na página **solicitações atrasadas ou imediatas** , aceite o padrão **enviar a solicitação imediatamente para uma opção de autoridade de certificação online** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="5afde-118">Na página **escolher uma CA (autoridade de certificação)** , clique na autoridade de certificação interna do Windows que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="5afde-119">Na página da **conta da autoridade de certificação** , especifique as credenciais alternativas a serem usadas se a conta na qual você está conectado não tiver autoridade suficiente para solicitar o certificado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="5afde-120">Na página **especificar modelo de certificado alternativo** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="5afde-121">Na página **configurações de nome e segurança** , você pode especificar um **nome amigável**, aceitar o comprimento da chave de 2048 bits e, em seguida, clicar em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="5afde-122">Na página **informações da organização** , especifique opcionalmente as informações da organização e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="5afde-123">Na página **informações** geográficas, opcionalmente, especifique informações geográficas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="5afde-124">Na página **nome do assunto/nomes alternativos de assunto** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5afde-125">A lista de nomes alternativos de entidades deve conter o nome do computador no qual você está instalando o diretor (se for um único diretor) ou o nome do pool de diretor e os nomes de URL simples configurados para a organização.</span><span class="sxs-lookup"><span data-stu-id="5afde-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="5afde-126">Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , selecione os **domínios SIP** configurados para todos os domínios que você deseja que o diretor manipule e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="5afde-127">Na página **configurar nomes alternativos de entidades adicionais** , adicione os nomes alternativos de entidades adicionais necessários e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="5afde-128">Na página **Resumo da solicitação de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="5afde-129">Na página **comandos em execução** , clique em **Avançar** depois que terminar a execução dos comandos.</span><span class="sxs-lookup"><span data-stu-id="5afde-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="5afde-130">Na página **status da solicitação de certificado online** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="5afde-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="5afde-131">Na página **atribuição de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5afde-132">Se você quiser exibir o certificado, clique duas vezes no certificado na lista.</span><span class="sxs-lookup"><span data-stu-id="5afde-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="5afde-133">Na página **Resumo de atribuição de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="5afde-134">Na página **comandos em execução** , clique em **concluir** após a conclusão da execução dos comandos.</span><span class="sxs-lookup"><span data-stu-id="5afde-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="5afde-135">Na página do **Assistente de certificado** , clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="5afde-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

