---
title: Gerenciar a autenticação de dois fatores no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumo: gerenciar a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818713"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="b951e-103">Gerenciar a autenticação de dois fatores no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b951e-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="b951e-104">**Resumo:** Gerenciar a autenticação de dois fatores no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b951e-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="b951e-105">A autenticação de dois fatores oferece maior segurança ao exigir que os usuários forneçam duas formas de autenticação ou identificação, ou seja, uma combinação de nome de usuário/senha e um token ou certificado.</span><span class="sxs-lookup"><span data-stu-id="b951e-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="b951e-106">Isso também é conhecido como "algo que você tem, algo que você conhece".</span><span class="sxs-lookup"><span data-stu-id="b951e-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="b951e-p102">Um exemplo típico da autenticação de dois fatores com um certificado é o uso de cartões inteligentes. Um cartão inteligente contém um certificado associado à conta do usuário e pode ser validado com as informações e certificado e usuário que estão armazenadas em um servidor. Ao comparar as informações do usuário (nome do usuário e senha) ao certificado fornecido, o servidor valida as credenciais e autentica o usuário.</span><span class="sxs-lookup"><span data-stu-id="b951e-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="b951e-110">Considere os seguintes assuntos ao configurar um ambiente do Skype for Business Server para dar suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="b951e-111">Suporte de Cliente</span><span class="sxs-lookup"><span data-stu-id="b951e-111">Client Support</span></span>

<span data-ttu-id="b951e-112">As atualizações cumulativas do Lync Server 2013: cliente de área de trabalho do 2013 de julho e do cliente Skype for Business são os únicos clientes que atualmente dão suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="b951e-113">Requisitos de topologia</span><span class="sxs-lookup"><span data-stu-id="b951e-113">Topology Requirements</span></span>

<span data-ttu-id="b951e-114">Os clientes são altamente incentivados a implantar a autenticação de dois fatores usando o Skype for Business Server dedicado com o Edge, o director e os pools de usuários.</span><span class="sxs-lookup"><span data-stu-id="b951e-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="b951e-115">Para habilitar a autenticação passiva para usuários, é necessário desabilitar outros métodos de autenticação para outras funções e serviços, tais como:</span><span class="sxs-lookup"><span data-stu-id="b951e-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="b951e-116">**Tipo de configuração**</span><span class="sxs-lookup"><span data-stu-id="b951e-116">**Configuration Type**</span></span>|<span data-ttu-id="b951e-117">**Tipo de serviço**</span><span class="sxs-lookup"><span data-stu-id="b951e-117">**Service Type**</span></span>|<span data-ttu-id="b951e-118">**Função do servidor**</span><span class="sxs-lookup"><span data-stu-id="b951e-118">**Server Role**</span></span>|<span data-ttu-id="b951e-119">**Tipo de autenticação a ser desabilitada**</span><span class="sxs-lookup"><span data-stu-id="b951e-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b951e-120">Serviço Web</span><span class="sxs-lookup"><span data-stu-id="b951e-120">Web Service</span></span>  <br/> |<span data-ttu-id="b951e-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="b951e-121">WebServer</span></span>  <br/> |<span data-ttu-id="b951e-122">Diretor</span><span class="sxs-lookup"><span data-stu-id="b951e-122">Director</span></span>  <br/> |<span data-ttu-id="b951e-123">Kerberos, NTLM e Certificado</span><span class="sxs-lookup"><span data-stu-id="b951e-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="b951e-124">Serviço Web</span><span class="sxs-lookup"><span data-stu-id="b951e-124">Web Service</span></span>  <br/> |<span data-ttu-id="b951e-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="b951e-125">WebServer</span></span>  <br/> |<span data-ttu-id="b951e-126">Front-End</span><span class="sxs-lookup"><span data-stu-id="b951e-126">Front End</span></span>  <br/> |<span data-ttu-id="b951e-127">Kerberos, NTLM e Certificado</span><span class="sxs-lookup"><span data-stu-id="b951e-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="b951e-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="b951e-128">Proxy</span></span>  <br/> |<span data-ttu-id="b951e-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="b951e-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="b951e-130">Borda</span><span class="sxs-lookup"><span data-stu-id="b951e-130">Edge</span></span>  <br/> |<span data-ttu-id="b951e-131">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="b951e-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="b951e-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="b951e-132">Proxy</span></span>  <br/> |<span data-ttu-id="b951e-133">Registrador</span><span class="sxs-lookup"><span data-stu-id="b951e-133">Registrar</span></span>  <br/> |<span data-ttu-id="b951e-134">Front-End</span><span class="sxs-lookup"><span data-stu-id="b951e-134">Front End</span></span>  <br/> |<span data-ttu-id="b951e-135">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="b951e-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="b951e-136">A não ser que esses tipos de autenticação estejam desabilitados no nível de serviço, todas as outras versões do cliente não conseguirão se conectar enquanto a autenticação de dois fatores estiver habilitada em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b951e-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="b951e-137">Descoberta de Serviços do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b951e-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="b951e-138">Os registros DNS usados por clientes internos e/ou externos para descobrir os serviços do Skype for Business devem ser configurados para resolver para um servidor do Skype for Business que não esteja habilitado para autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="b951e-139">Com essa configuração, os usuários de pools do Skype for Business que não estão habilitados para a autenticação de dois fatores não serão necessários para inserir um PIN para autenticação, enquanto os usuários de pools do Skype for Business habilitados para a autenticação de dois fatores serão obrigatório para inserir o PIN para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b951e-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="b951e-140">Autenticação do Exchange</span><span class="sxs-lookup"><span data-stu-id="b951e-140">Exchange Authentication</span></span>

<span data-ttu-id="b951e-141">Os clientes que implantaram a autenticação de dois fatores para o Microsoft Exchange podem descobrir que determinados recursos do cliente não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b951e-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="b951e-142">Isso, no momento, é o design, pois o cliente Skype for Business não oferece suporte à autenticação de dois fatores para recursos que dependem da integração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b951e-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="b951e-143">Contatos</span><span class="sxs-lookup"><span data-stu-id="b951e-143">Contacts</span></span>

<span data-ttu-id="b951e-144">Os usuários do Skype for Business que estiverem configurados para aproveitar o recurso de repositório de contatos unificado acharão que seus contatos não estarão mais disponíveis depois de entrar com a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="b951e-145">Você deve usar o cmdlet **Invoke-CsUcsRollback** para remover os contatos do usuário existentes do repositório de contatos unificado e armazená-los no Skype for Business Server antes de habilitar a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="b951e-146">Pesquisa de Habilidades</span><span class="sxs-lookup"><span data-stu-id="b951e-146">Skill Search</span></span>

<span data-ttu-id="b951e-147">Os clientes que configuraram o recurso de pesquisa de habilidades no ambiente do Skype for Business acharão que esse recurso não funciona quando o Skype for Business estiver habilitado para autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="b951e-148">Isso ocorre devido ao projeto, já que o Microsoft SharePoint não é compatível com a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="b951e-149">Credenciais</span><span class="sxs-lookup"><span data-stu-id="b951e-149">Credentials</span></span>

<span data-ttu-id="b951e-150">Há várias considerações de implantação envolvendo as credenciais do Skype for Business salvas, que podem afetar os usuários configurados para usar a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="b951e-151">Exclusão de Credenciais Salvas</span><span class="sxs-lookup"><span data-stu-id="b951e-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="b951e-152">Os usuários devem usar a opção **excluir minhas informações de entrada** no cliente Skype for Business e excluir a pasta de perfil SIP do%LocalAppData%\Microsoft\Office\15.0\Skype for Business antes de tentarem se conectar pela primeira vez usando a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="b951e-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b951e-153">DisableNTCredentials</span></span>

<span data-ttu-id="b951e-154">Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b951e-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="b951e-155">Em uma implantação típica do Skype for Business Server na qual Kerberos e/ou NTLM está habilitado para autenticação, os usuários não devem digitar as credenciais toda vez que entrarem.</span><span class="sxs-lookup"><span data-stu-id="b951e-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="b951e-156">Se as credenciais dos usuários forem inadvertidamente solicitadas antes de ser necessário informar o PIN, a chave de registro **DisableNTCredentials** pode estar configurada por engano nos computadores clientes, possivelmente através de uma Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="b951e-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="b951e-157">Para impedir o prompt adicional de credenciais, crie a seguinte entrada do registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários de um determinado pool usando a política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="b951e-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="b951e-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="b951e-158">SavePassword</span></span>

<span data-ttu-id="b951e-159">Quando um usuário entrar no Skype for Business pela primeira vez, o usuário será solicitado a salvar sua senha.</span><span class="sxs-lookup"><span data-stu-id="b951e-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="b951e-160">Se selecionada, essa opção permite que o certificado de cliente do usuário seja armazenado no repositório de certificados pessoal e as credenciais do Windows do usuário sejam armazenadas no Gerenciador de credenciais do computador local.</span><span class="sxs-lookup"><span data-stu-id="b951e-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="b951e-161">A configuração do registro **SavePassword** deve ser desabilitada quando o Skype for Business for configurado para dar suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b951e-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="b951e-162">Para impedir que os usuários salvem suas senhas, altere a seguinte entrada do registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários de um determinado pool usando a política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="b951e-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="b951e-163">AD FS 2.0 Token Replay</span><span class="sxs-lookup"><span data-stu-id="b951e-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="b951e-p110">O AD FS 2.0 oferece um recurso chamado detecção de repetição de token, pelo qual é possível detectar várias solicitações de token que usam o mesmo token a fim de descartá-las. Quanto este recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação tanto no perfil passivo do WS-Federation quanto no perfil de SAML WebSSO, certificando-se de que o mesmo token nunca é usado mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="b951e-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="b951e-166">Esse recurso deve ser habilitado em situações em que há grandes preocupações com a segurança, como quando se usa quiosques.</span><span class="sxs-lookup"><span data-stu-id="b951e-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="b951e-167">Para obter mais informações sobre a detecção de repetição de token, consulte [práticas recomendadas para o planejamento seguro e a implantação do AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="b951e-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="b951e-168">Acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="b951e-168">External User Access</span></span>

<span data-ttu-id="b951e-169">A configuração de um proxy ADFS ou de proxy reverso para dar suporte à autenticação de dois fatores do Skype for Business a partir de redes externas não é abordada nestes tópicos.</span><span class="sxs-lookup"><span data-stu-id="b951e-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b951e-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="b951e-170">See also</span></span>

[<span data-ttu-id="b951e-171">Configurar a autenticação de dois fatores no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b951e-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
