---
title: Gerenciar a autenticação de dois fatores no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumo: Gerencie autenticação de dois fatores no Skype para Business Server.'
ms.openlocfilehash: 04aaf552238b5aa693d95dbb232f49c0045f4a12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919483"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="5e29a-103">Gerenciar a autenticação de dois fatores no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5e29a-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="5e29a-104">**Resumo:** Gerencie a autenticação de dois fatores no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5e29a-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="5e29a-105">A autenticação de dois fatores oferece maior segurança ao exigir que os usuários forneçam duas formas de autenticação ou identificação, ou seja, uma combinação de nome de usuário/senha e um token ou certificado.</span><span class="sxs-lookup"><span data-stu-id="5e29a-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="5e29a-106">Isso também é conhecida como "algo que você tem, algo que você conhece."</span><span class="sxs-lookup"><span data-stu-id="5e29a-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="5e29a-p102">Um exemplo típico da autenticação de dois fatores com um certificado é o uso de cartões inteligentes. Um cartão inteligente contém um certificado associado à conta do usuário e pode ser validado com as informações e certificado e usuário que estão armazenadas em um servidor. Ao comparar as informações do usuário (nome do usuário e senha) ao certificado fornecido, o servidor valida as credenciais e autentica o usuário.</span><span class="sxs-lookup"><span data-stu-id="5e29a-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="5e29a-110">Ao configurar um Skype para ambiente de servidor de negócios para suportar a autenticação de dois fatores, considere os seguintes assuntos.</span><span class="sxs-lookup"><span data-stu-id="5e29a-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="5e29a-111">Suporte de Cliente</span><span class="sxs-lookup"><span data-stu-id="5e29a-111">Client Support</span></span>

<span data-ttu-id="5e29a-112">As atualizações cumulativas do Lync Server 2013: julho de 2013 cliente de desktop e do Skype para o cliente de negócios são os únicos clientes que oferecem suporte a autenticação de dois fatores no momento.</span><span class="sxs-lookup"><span data-stu-id="5e29a-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="5e29a-113">Requisitos de topologia</span><span class="sxs-lookup"><span data-stu-id="5e29a-113">Topology Requirements</span></span>

<span data-ttu-id="5e29a-114">Os clientes são altamente encorajados implantar a autenticação de dois fatores usando Skype dedicado para Business Server com borda, diretor e Pools de usuário.</span><span class="sxs-lookup"><span data-stu-id="5e29a-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="5e29a-115">Para habilitar a autenticação passiva para usuários, é necessário desabilitar outros métodos de autenticação para outras funções e serviços, tais como:</span><span class="sxs-lookup"><span data-stu-id="5e29a-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="5e29a-116">**Tipo de configuração**</span><span class="sxs-lookup"><span data-stu-id="5e29a-116">**Configuration Type**</span></span>|<span data-ttu-id="5e29a-117">**Tipo de serviço**</span><span class="sxs-lookup"><span data-stu-id="5e29a-117">**Service Type**</span></span>|<span data-ttu-id="5e29a-118">**Função de servidor**</span><span class="sxs-lookup"><span data-stu-id="5e29a-118">**Server Role**</span></span>|<span data-ttu-id="5e29a-119">**Tipo de autenticação a ser desabilitada**</span><span class="sxs-lookup"><span data-stu-id="5e29a-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e29a-120">Serviço Web</span><span class="sxs-lookup"><span data-stu-id="5e29a-120">Web Service</span></span>  <br/> |<span data-ttu-id="5e29a-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="5e29a-121">WebServer</span></span>  <br/> |<span data-ttu-id="5e29a-122">Diretor</span><span class="sxs-lookup"><span data-stu-id="5e29a-122">Director</span></span>  <br/> |<span data-ttu-id="5e29a-123">Kerberos, NTLM e Certificado</span><span class="sxs-lookup"><span data-stu-id="5e29a-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="5e29a-124">Serviço Web</span><span class="sxs-lookup"><span data-stu-id="5e29a-124">Web Service</span></span>  <br/> |<span data-ttu-id="5e29a-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="5e29a-125">WebServer</span></span>  <br/> |<span data-ttu-id="5e29a-126">Front-End</span><span class="sxs-lookup"><span data-stu-id="5e29a-126">Front End</span></span>  <br/> |<span data-ttu-id="5e29a-127">Kerberos, NTLM e Certificado</span><span class="sxs-lookup"><span data-stu-id="5e29a-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="5e29a-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="5e29a-128">Proxy</span></span>  <br/> |<span data-ttu-id="5e29a-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="5e29a-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="5e29a-130">Borda</span><span class="sxs-lookup"><span data-stu-id="5e29a-130">Edge</span></span>  <br/> |<span data-ttu-id="5e29a-131">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="5e29a-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="5e29a-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="5e29a-132">Proxy</span></span>  <br/> |<span data-ttu-id="5e29a-133">Registrador</span><span class="sxs-lookup"><span data-stu-id="5e29a-133">Registrar</span></span>  <br/> |<span data-ttu-id="5e29a-134">Front-End</span><span class="sxs-lookup"><span data-stu-id="5e29a-134">Front End</span></span>  <br/> |<span data-ttu-id="5e29a-135">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="5e29a-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="5e29a-136">A não ser que esses tipos de autenticação estejam desabilitados no nível de serviço, todas as outras versões do cliente não conseguirão se conectar enquanto a autenticação de dois fatores estiver habilitada em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="5e29a-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="5e29a-137">Descoberta de Serviços do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e29a-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="5e29a-138">Registros DNS usados pelos clientes internos e/ou externos para descobrir Skype para serviços corporativos de devem ser configurados para ser resolvido para um Skype para Business server não está habilitado para a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="5e29a-139">Com essa configuração, os usuários do Skype para os Pools de negócios que não estão habilitados para autenticação de dois fatores não precisará inserir um PIN para autenticar, enquanto os usuários do Skype para Pools de negócios que estão habilitados para autenticação de dois fatores serão precisarão para inserir o PIN para autenticar.</span><span class="sxs-lookup"><span data-stu-id="5e29a-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="5e29a-140">Autenticação do Exchange</span><span class="sxs-lookup"><span data-stu-id="5e29a-140">Exchange Authentication</span></span>

<span data-ttu-id="5e29a-141">Clientes que implantaram autenticação de dois fatores para o Microsoft Exchange podem achar que certos recursos no cliente não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5e29a-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="5e29a-142">Isso é atualmente por design, pois o Skype para o cliente de negócios não dá suporte a autenticação de dois fatores para recursos que dependem de integração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5e29a-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="5e29a-143">Contatos</span><span class="sxs-lookup"><span data-stu-id="5e29a-143">Contacts</span></span>

<span data-ttu-id="5e29a-144">Skype para usuários de negócios que estiverem configurados para aproveitar o recurso de repositório unificado de contatos encontrará que seus contatos não estão mais disponíveis após entrar com autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="5e29a-145">Você deve usar o cmdlet **Invoke-CsUcsRollback** remover contatos do usuário existente do repositório unificado de contatos e armazená-los no Skype para Business Server antes de habilitar a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="5e29a-146">Pesquisa de Habilidades</span><span class="sxs-lookup"><span data-stu-id="5e29a-146">Skill Search</span></span>

<span data-ttu-id="5e29a-147">Os clientes que configuraram o recurso de pesquisa de habilidade em seu Skype para ambiente de negócios encontrará que esse recurso não funciona quando Skype para a empresa está habilitado para a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="5e29a-148">Isso ocorre devido ao projeto, já que o Microsoft SharePoint não é compatível com a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="5e29a-149">Credenciais</span><span class="sxs-lookup"><span data-stu-id="5e29a-149">Credentials</span></span>

<span data-ttu-id="5e29a-150">Há várias considerações de implantação envolvendo salva Skype para credenciais de negócios que pode afetar os usuários configurados para usar a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="5e29a-151">Exclusão de Credenciais Salvas</span><span class="sxs-lookup"><span data-stu-id="5e29a-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="5e29a-152">Usuários devem usar a opção **Excluir minhas informações de entrar** no Skype para o cliente de negócios e excluir sua pasta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype for Business antes de tentar entrar pela primeira vez usando dois fatores autenticação.</span><span class="sxs-lookup"><span data-stu-id="5e29a-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="5e29a-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="5e29a-153">DisableNTCredentials</span></span>

<span data-ttu-id="5e29a-154">Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação.</span><span class="sxs-lookup"><span data-stu-id="5e29a-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="5e29a-155">Em um Skype típica para implantação Business Server onde o Kerberos e/ou NTLM está habilitado para autenticação, os usuários não devem ter que inserir suas credenciais cada vez que entrarem.</span><span class="sxs-lookup"><span data-stu-id="5e29a-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="5e29a-156">Se as credenciais dos usuários forem inadvertidamente solicitadas antes de ser necessário informar o PIN, a chave de registro **DisableNTCredentials** pode estar configurada por engano nos computadores clientes, possivelmente através de uma Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="5e29a-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="5e29a-157">Para impedir que a solicitação adicional de credenciais, crie a seguinte entrada de registro na estação de trabalho local ou usar o Skype para o modelo administrativo de negócios para aplicar a todos os usuários de um determinado pool usando a diretiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="5e29a-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="5e29a-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="5e29a-158">SavePassword</span></span>

<span data-ttu-id="5e29a-159">Quando um usuário entra no Skype para negócios pela primeira vez, o usuário é solicitado a salvar sua senha.</span><span class="sxs-lookup"><span data-stu-id="5e29a-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="5e29a-160">Se selecionada, esta opção permite que o certificado de cliente do usuário a serem armazenados no repositório de certificados pessoais e credenciais do Windows do usuário a serem armazenados no Gerenciador de credencial do computador local.</span><span class="sxs-lookup"><span data-stu-id="5e29a-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="5e29a-161">A configuração de registro **SavePassword** deve ser desabilitada quando Skype para negócios é configurado para oferecer suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="5e29a-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="5e29a-162">Para impedir usuários de salvar suas senhas, altere a seguinte entrada do registro na estação de trabalho local ou use o Skype para o modelo administrativo de negócios para aplicar a todos os usuários para um determinado pool usando a diretiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="5e29a-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="5e29a-163">AD FS 2.0 Token Replay</span><span class="sxs-lookup"><span data-stu-id="5e29a-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="5e29a-p110">O AD FS 2.0 oferece um recurso chamado detecção de repetição de token, pelo qual é possível detectar várias solicitações de token que usam o mesmo token a fim de descartá-las. Quanto este recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação tanto no perfil passivo do WS-Federation quanto no perfil de SAML WebSSO, certificando-se de que o mesmo token nunca é usado mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="5e29a-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="5e29a-166">Esse recurso deve ser habilitado em situações em que há grandes preocupações com a segurança, como quando se usa quiosques.</span><span class="sxs-lookup"><span data-stu-id="5e29a-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="5e29a-167">Para obter mais informações sobre detecção de reprodução de token, consulte [Práticas recomendadas para proteger o planejamento e implantação do AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="5e29a-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="5e29a-168">Acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="5e29a-168">External User Access</span></span>

<span data-ttu-id="5e29a-169">Configurando um Proxy do ADFS ou Proxy reverso para suportar Skype para autenticação de dois fatores comerciais de redes externas não é abordada nestes tópicos.</span><span class="sxs-lookup"><span data-stu-id="5e29a-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e29a-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="5e29a-170">See also</span></span>

[<span data-ttu-id="5e29a-171">Configurar a autenticação de dois fatores no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5e29a-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
