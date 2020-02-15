---
title: 'Lync Server 2013: configurar certificados para o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e036073f3e617bff993bd38b356d3ac76f73d57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="4de5b-102">Configurar certificados para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4de5b-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4de5b-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4de5b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4de5b-104">Ao executar o Assistente de certificado, certifique-se de que esteja conectado usando uma conta membro de um grupo com as permissões apropriadas para o tipo de modelo de certificado que será usado.</span><span class="sxs-lookup"><span data-stu-id="4de5b-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="4de5b-105">Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado do servidor Web.</span><span class="sxs-lookup"><span data-stu-id="4de5b-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="4de5b-106">Se você usar uma conta membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões Inscrever exigidas para usar esse modelo.</span><span class="sxs-lookup"><span data-stu-id="4de5b-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="4de5b-107">Cada Diretor requer um certificado padrão, um certificado da Web interno e um externo.</span><span class="sxs-lookup"><span data-stu-id="4de5b-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="4de5b-108">Para obter detalhes sobre os requisitos de certificado para diretores, consulte [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4de5b-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="4de5b-109">Use o procedimento a seguir para configurar os certificados do diretor.</span><span class="sxs-lookup"><span data-stu-id="4de5b-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="4de5b-110">Repita o procedimento para cada diretor.</span><span class="sxs-lookup"><span data-stu-id="4de5b-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="4de5b-111">As etapas deste procedimento descrevem como configurar um certificado de uma autoridade de certificação raiz corporativa interna (AC) implantada pela sua organização e com o processamento de solicitação offline.</span><span class="sxs-lookup"><span data-stu-id="4de5b-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="4de5b-112">Para obter detalhes sobre como obter certificados de uma autoridade de certificação externa, entre em contato com a equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="4de5b-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="4de5b-113">Para configurar certificados para o diretor ou pool de diretor</span><span class="sxs-lookup"><span data-stu-id="4de5b-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="4de5b-114">No assistente de implantação do Lync Server, ao lado de **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="4de5b-115">Na página **Assistente de Certificados**, clique em **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="4de5b-116">Na página **Solicitação de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="4de5b-117">Na página **solicitações atrasadas ou imediatas** , aceite a opção padrão **enviar a solicitação imediatamente para uma autoridade de certificação online** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="4de5b-118">Na página **escolher uma autoridade de certificação (CA)** , clique na autoridade de certificação interna do Windows que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="4de5b-119">Na página **conta da autoridade de certificação** , especifique as credenciais alternativas a serem usadas se a conta com a qual você está conectado não tiver autoridade suficiente para solicitar o certificado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="4de5b-120">Na página **Especificar Modelo de Certificado Alternativo**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="4de5b-121">Na página **nome e configurações de segurança** , é possível especificar um **nome amigável**, aceitar o comprimento da chave 2048 bits e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="4de5b-122">Na página **Informações da Organização**, especifique, como opção, as informações da organização e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="4de5b-123">Na página **Informações Geográficas**, especifique, como opção, as informações geográficas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="4de5b-124">Na página **nome do assunto/nomes alternativos da entidade** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4de5b-125">A lista de nomes alternativos da entidade deve conter o nome do computador no qual você está instalando o diretor (se um único diretor) ou o nome do pool de diretor e os nomes de URL simples configurados para a organização.</span><span class="sxs-lookup"><span data-stu-id="4de5b-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="4de5b-126">Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , selecione os **domínios SIP configurados** para todos os domínios que você deseja que o diretor manipule e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="4de5b-127">Na página **Configurar Nomes Alternativos de Entidade Adicionais**, adicione quaisquer outros nomes alternativos de entidade necessários e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="4de5b-128">Na página **Resumo da Solicitação de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="4de5b-129">Na página **executando comandos** , clique em **Avançar** após a conclusão da execução dos comandos.</span><span class="sxs-lookup"><span data-stu-id="4de5b-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="4de5b-130">Na página **Status da Solicitação de Certificado Online**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="4de5b-131">Na página **Atribuição de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4de5b-132">Se você quiser exibir o certificado, clique duas vezes no certificado na lista.</span><span class="sxs-lookup"><span data-stu-id="4de5b-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="4de5b-133">Na página **Resumo da Atribuição de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="4de5b-134">Na página **executando comandos** , clique em **concluir** após a conclusão da execução dos comandos.</span><span class="sxs-lookup"><span data-stu-id="4de5b-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="4de5b-135">Na página **Assistente de Certificado**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="4de5b-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

