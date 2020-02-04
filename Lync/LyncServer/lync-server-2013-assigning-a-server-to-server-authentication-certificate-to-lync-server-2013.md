---
title: Atribuindo um certificado de autenticação de servidor a servidor ao Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="4b9d5-102">Atribuindo um certificado de autenticação de servidor a servidor ao Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b9d5-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9d5-103">_**Tópico da última modificação:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="4b9d5-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="4b9d5-104">Para determinar se um certificado de autenticação de servidor para servidor já foi atribuído ao Microsoft Lync Server 2013, execute o seguinte comando no Shell de gerenciamento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="4b9d5-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="4b9d5-105">Se nenhuma informação de certificado for retornada, você deverá atribuir um certificado emissor de token antes de poder usar a autenticação servidor- servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="4b9d5-106">Como regra geral, qualquer certificado do Lync Server 2013 pode ser usado como seu certificado do OAuthTokenIssuer; por exemplo, seu certificado padrão do Lync Server 2013 também pode ser usado como o certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="4b9d5-107">(O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo assunto.) Os dois requisitos principais para o certificado usado para a autenticação de servidor para servidor são estes: 1) o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus servidores front-end; e 2) o certificado deve ter pelo menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="4b9d5-108">Se você não tiverum certificado que possa ser usado para autenticação servidor-servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor-servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="4b9d5-109">Depois de solicitar e obter o novo certificado, você pode fazer logon em qualquer um dos seus servidores front-end e usar um comando do Windows PowerShell semelhante a este para importar e atribuir esse certificado:</span><span class="sxs-lookup"><span data-stu-id="4b9d5-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="4b9d5-110">No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="4b9d5-111">Este procedimento deve ser executado apenas uma vez: o serviço de replicação do Lync Server criará automaticamente um conjunto de tarefas agendadas que descriptografarão e implantarão o certificado em todos os seus servidores front-ends.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="4b9d5-112">Como alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor-servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="4b9d5-113">(Conforme observado, o certificado padrão pode ser usado como certificado de autenticação de servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade de impressão digital do certificado padrão e, em seguida, usa esse valor para torná-lo o certificado padrão do certificado de autenticação de servidor para servidor:</span><span class="sxs-lookup"><span data-stu-id="4b9d5-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="4b9d5-114">No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação de servidor para servidor global; Isso significa que o certificado será replicado para e usado por todos os seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="4b9d5-115">Novamente, esse comando só deve ser executado uma vez e somente em um dos seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="4b9d5-116">Apesar de todos os servidores front-end precisarem usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="4b9d5-117">Em vez disso, configure o certificado uma vez, deixe o servidor de replicação do Lync Server cuidar do cópia desse certificado para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="4b9d5-118">O cmdlet Set-CsCertificate leva o certificado em questão e configura imediatamente esse certificado para atuar como o certificado OAuthTokenIssuer atual.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="4b9d5-119">(O Lync Server 2013 mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado comece imediatamente a atuar como o certificado OAuthTokenIssuer, use o cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="4b9d5-120">Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="4b9d5-121">"Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="4b9d5-122">Por exemplo, esse comando recupera o certificado padrão e, em seguida, configura esse certificado para assumir como o certificado atual do OAuthTokenIssuer a partir de 1 ° de julho de 2012:</span><span class="sxs-lookup"><span data-stu-id="4b9d5-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="4b9d5-123">Em 1º de julho de 2012, o novo certificado será configurado como o atual certificado de OAuthTokenIssuer e o certificado de OAuthTokenIssuer "antigo" será configurado como o certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="4b9d5-124">Se não quiser usar o Windows PowerShell, você também pode usar o console MMC de certificados para exportar um certificado de um servidor front-end e, em seguida, importar esse mesmo certificado em todos os outros servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="4b9d5-125">Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="4b9d5-126">Nesse caso, o procedimento deve ser executado em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="4b9d5-127">Ao exportar e importar certificados dessa maneira, o Lync Server 2013 não replicará esse certificado para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="4b9d5-128">Após a importação do certificado para todos os seus servidores front-end, esse certificado pode ser atribuído usando o assistente de implantação do Lync Server em vez do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="4b9d5-129">Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador no qual o Assistente de Implantação tenha sido instalado:</span><span class="sxs-lookup"><span data-stu-id="4b9d5-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="4b9d5-130">Clique em Iniciar, em todos os programas, em **Microsoft Lync Server 2013**e, em seguida, clique em **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="4b9d5-131">No assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="4b9d5-132">Na página Microsoft Lync Server 2013, clique no botão **executar** abaixo do título **etapa 3: solicitar, instalar ou atribuir certificados**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="4b9d5-133">(Observação: Se você já tiver instalado certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)</span><span class="sxs-lookup"><span data-stu-id="4b9d5-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="4b9d5-134">No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="4b9d5-135">No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="4b9d5-136">Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor-servidor e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="4b9d5-137">Na página Resumo da Atribuição de Certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="4b9d5-138">Na página Executando Comandos, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="4b9d5-139">Feche o Assistente de Certificado e Assistente de Implantação.</span><span class="sxs-lookup"><span data-stu-id="4b9d5-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

