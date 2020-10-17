---
title: Atribuindo um certificado de autenticação de servidor para servidor ao Lync Server 2013
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
ms.openlocfilehash: ec8ac614cdc829ab2b1efd7d6ff9179c33d5a33e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499468"
---
# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="36ed2-102">Atribuindo um certificado de autenticação de servidor para servidor ao Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ed2-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ed2-103">_**Última modificação do tópico:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="36ed2-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="36ed2-104">Para determinar se um certificado de autenticação de servidor para servidor já foi atribuído ao Microsoft Lync Server 2013, execute o seguinte comando no Shell de gerenciamento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="36ed2-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="36ed2-105">Se nenhuma informação de certificado é retornada, você deve atribuir um certificado emissor de token antes de poder usar a autenticação servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="36ed2-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="36ed2-106">Como regra geral, qualquer certificado do Lync Server 2013 pode ser usado como seu certificado OAuthTokenIssuer; por exemplo, seu certificado padrão do Lync Server 2013 também pode ser usado como o certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="36ed2-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="36ed2-107">(O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo assunto.) Os dois requisitos principais para o certificado usado para a autenticação de servidor para servidor são: 1) o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus servidores front-end; e 2) o certificado deve ter pelo menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="36ed2-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="36ed2-p102">Se você não possui um certificado que pode ser usado para autenticação servidor para servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor para servidor. Após ter solicitado e obtido o novo certificado, é possível fazer o login para qualquer um de seus Servidores de Front-End e usar um comando do Windows PowerShell semelhante a este para importar e atribuir este certificado:</span><span class="sxs-lookup"><span data-stu-id="36ed2-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="36ed2-p103">No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado. Este procedimento deve ser executado apenas uma vez: O serviço de replicação do Lync Server irá criar automaticamente um conjunto de tarefas programadas que irão criptografar e implantar o certificado em todos os seus Servidores de Front-End.</span><span class="sxs-lookup"><span data-stu-id="36ed2-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="36ed2-p104">Em alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor para servidor. (Conforme observado, o certificado padrão pode ser usado como o certificado de autenticação servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade Thumbprint do certificado padrão, use este valor para tornar o certificado padrão o certificado de autenticação servidor para servidor:</span><span class="sxs-lookup"><span data-stu-id="36ed2-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="36ed2-p105">No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação servidor para servidor global; isto significa que o certificado será replicado e usado por todos os seus Servidores de Front-End. Novamente, este comando deve ser executado apenas uma vez e apenas em um de seus Servidores de Front-End. Embora todos os Servidores de Front-End devam usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada Servidor de Front-End. Ao invés disso, configure o certificado uma vez, permita que o servidor de replicação do Lync Server cuide da cópia deste certificado em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="36ed2-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="36ed2-118">O cmdlet Set-CsCertificate Obtém o certificado em questão e imediatamente configura esse certificado para atuar como o certificado OAuthTokenIssuer atual.</span><span class="sxs-lookup"><span data-stu-id="36ed2-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="36ed2-119">(Lync Server 2013 mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado inicie imediatamente o Act como o certificado OAuthTokenIssuer, use o cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="36ed2-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="36ed2-p107">Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado. "Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo. Por exemplo, este comando recupera o certificado padrão e configura este certificado para assumir como o certificado OAuthTokenIssuer atual a partir de 1° de julho de 2012:</span><span class="sxs-lookup"><span data-stu-id="36ed2-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="36ed2-123">Em 1° de julho de 2012, o novo certificado será configurado como o certificado OAuthTokenIssuer atual e o certificado OAuthTokenIssuer "antigo" será configurado como o certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="36ed2-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="36ed2-p108">Se você não deseja usar o Windows PowerShell, é possível também usar o console MMC de Certificados para exportar um certificado de um Servidor de Front-End e importar este mesmo certificado em todos os seus outros Servidores de Front-End. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.</span><span class="sxs-lookup"><span data-stu-id="36ed2-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="36ed2-126">Neste caso, o procedimento deve ser realizado em cada Servidor de Front-End.</span><span class="sxs-lookup"><span data-stu-id="36ed2-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="36ed2-127">Ao exportar e importar certificados dessa maneira, o Lync Server 2013 não replicará esse certificado para cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="36ed2-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="36ed2-128">Depois que o certificado for importado para todos os seus servidores front-end, esse certificado poderá ser atribuído usando o assistente de implantação do Lync Server em vez do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36ed2-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="36ed2-129">Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador onde o Assistente de Implantação foi instalado:</span><span class="sxs-lookup"><span data-stu-id="36ed2-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="36ed2-130">Clique em Iniciar, em todos os programas, em **Microsoft Lync Server 2013**e em **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="36ed2-131">No Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="36ed2-132">Na página Microsoft Lync Server 2013, clique no botão **executar** no título **etapa 3: solicitar, instalar ou atribuir certificados**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="36ed2-133">(Observação: Se você já instalou certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)</span><span class="sxs-lookup"><span data-stu-id="36ed2-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="36ed2-134">No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="36ed2-135">No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="36ed2-136">Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor para servidor e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="36ed2-137">Na página Resumo da Atribuição de Certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="36ed2-138">Na página Executando Comandos, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="36ed2-139">Feche o Assistente de Certificado e Assistente de Implantação.</span><span class="sxs-lookup"><span data-stu-id="36ed2-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

