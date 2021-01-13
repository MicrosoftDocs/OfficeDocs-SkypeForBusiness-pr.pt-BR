---
title: Atribuir um certificado de autenticação de servidor para servidor ao Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumo: atribua um certificado de autenticação de servidor para servidor para o Skype for Business Server.'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828501"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="fd8bc-103">Atribuir um certificado de autenticação de servidor para servidor ao Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd8bc-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="fd8bc-104">**Resumo:** Atribua um certificado de autenticação de servidor para servidor para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="fd8bc-105">Para determinar se um certificado de autenticação servidor para servidor já foi atribuído ao Skype for Business Server, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="fd8bc-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="fd8bc-106">Se nenhuma informação de certificado é retornada, você deve atribuir um certificado emissor de token antes de poder usar a autenticação servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="fd8bc-107">Como regra geral, qualquer certificado do Skype for Business Server pode ser usado como seu certificado OAuthTokenIssuer; por exemplo, seu certificado padrão do Skype for Business Server também pode ser usado como o certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="fd8bc-108">(O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo Assunto.) Os dois principais requisitos para o certificado usado para autenticação servidor para servidor são: 1)o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os servidores front-end; e, 2) o certificado deve ter pelo menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="fd8bc-p102">Se você não possui um certificado que pode ser usado para autenticação servidor para servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor para servidor. Após ter solicitado e obtido o novo certificado, é possível fazer o login para qualquer um de seus Servidores de Front-End e usar um comando do Windows PowerShell semelhante a este para importar e atribuir este certificado:</span><span class="sxs-lookup"><span data-stu-id="fd8bc-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="fd8bc-111">No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="fd8bc-112">Esse procedimento deve ser executado apenas uma vez: o serviço de replicação do Skype for Business Server criará automaticamente um conjunto de tarefas agendadas que descriptografará e implantará o certificado em todos os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="fd8bc-p104">Em alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor para servidor. (Conforme observado, o certificado padrão pode ser usado como o certificado de autenticação servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade Thumbprint do certificado padrão, use este valor para tornar o certificado padrão o certificado de autenticação servidor para servidor:</span><span class="sxs-lookup"><span data-stu-id="fd8bc-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="fd8bc-115">No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação servidor para servidor global; isto significa que o certificado será replicado e usado por todos os seus Servidores de Front-End.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="fd8bc-116">Novamente, este comando deve ser executado apenas uma vez e apenas em um de seus Servidores de Front-End.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="fd8bc-117">Embora todos os Servidores de Front-End devam usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada Servidor de Front-End.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="fd8bc-118">Em vez disso, configure o certificado uma vez e deixe que o servidor de replicação do Skype for Business Server tome cuidado ao copiar esse certificado para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="fd8bc-119">O Set-CsCertificate cmdlet recebe o certificado em questão e configura imediatamente esse certificado para agir como o certificado OAuthTokenIssuer atual.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="fd8bc-120">(O Skype for Business Server mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado comece imediatamente a agir como o certificado OAuthTokenIssuer, use o Set-CsCertificate cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="fd8bc-121">Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="fd8bc-122">"Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="fd8bc-123">Por exemplo, este comando recupera o certificado padrão e configura esse certificado para assumir como o certificado OAuthTokenIssuer atual a partir de 1º de julho de 2015:</span><span class="sxs-lookup"><span data-stu-id="fd8bc-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="fd8bc-124">Em 1º de julho de 2015, o novo certificado será configurado como o certificado OAuthTokenIssuer atual e o certificado OAuthTokenIssuer "antigo" será configurado como o certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="fd8bc-p108">Se você não deseja usar o Windows PowerShell, é possível também usar o console MMC de Certificados para exportar um certificado de um Servidor de Front-End e importar este mesmo certificado em todos os seus outros Servidores de Front-End. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fd8bc-127">Neste caso, o procedimento deve ser realizado em cada Servidor de Front-End.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="fd8bc-128">Ao exportar e importar certificados dessa maneira, o Skype for Business Server não replicará esse certificado para cada Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="fd8bc-129">Depois que o certificado tiver sido importado para todos os servidores front-end, esse certificado poderá ser atribuído usando o Assistente de Implantação do Skype for Business Server em vez do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="fd8bc-130">Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador onde o Assistente de Implantação foi instalado:</span><span class="sxs-lookup"><span data-stu-id="fd8bc-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="fd8bc-131">Clique em Iniciar, em Todos os Programas, no **Skype for Business Server** e no Assistente de Implantação do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="fd8bc-132">No Assistente de Implantação, clique **em Instalar ou Atualizar o Sistema do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="fd8bc-133">Na página Do Skype for  Business Server, clique no botão Executar sob o título **Etapa 3: Solicitar, Instalar ou Atribuir Certificados.**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="fd8bc-134">(Observação: Se você já instalou certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)</span><span class="sxs-lookup"><span data-stu-id="fd8bc-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="fd8bc-135">No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="fd8bc-136">No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="fd8bc-137">Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor para servidor e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="fd8bc-138">Na página Resumo da Atribuição de Certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="fd8bc-139">Na página Executando Comandos, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="fd8bc-140">Feche o Assistente de Certificado e Assistente de Implantação.</span><span class="sxs-lookup"><span data-stu-id="fd8bc-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

