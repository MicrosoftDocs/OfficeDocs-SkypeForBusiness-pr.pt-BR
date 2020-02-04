---
title: 'Lync Server 2013: Configurando políticas de inicialização do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8258063645267fb12801548ddfdeae1b4ef7c795
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="020da-102">Configurando as políticas de inicialização do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020da-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="020da-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="020da-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="020da-104">O Console de Gerenciamento de Política de Grupo (GPMC) e o Editor de Objeto de Política de Grupo são ferramentas que você utiliza para gerenciar Políticas de Grupo.</span><span class="sxs-lookup"><span data-stu-id="020da-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="020da-105">Incluído no modelo administrativo da política de grupo do Office há modelos administrativos do Lync 2013. admx (ADMX) e. adml (ADML), que contêm as configurações de política baseadas no registro que você configura para objetos de política de grupo no domínio.</span><span class="sxs-lookup"><span data-stu-id="020da-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="020da-106">Os arquivos ADML são complementos específicos de idioma para arquivos ADMX.</span><span class="sxs-lookup"><span data-stu-id="020da-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="020da-107">Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="020da-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="020da-108">Para obter mais informações, consulte "arquivos de modelo administrativo do Office 2013 (ADMX, ADML)" na documentação do <http://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 em.</span><span class="sxs-lookup"><span data-stu-id="020da-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="020da-109">Para o Lync 2013, há várias políticas de inicialização do cliente que você deve considerar Configurando antes de os usuários entrarem no servidor pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="020da-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="020da-110">Por exemplo, os servidores padrão e o modo de segurança que o cliente deve utilizar até que a entrada esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="020da-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="020da-111">Você pode usar uma Política de Grupo para estabelecer essas configurações nos Registros dos computadores dos usuários antes que eles entrem e comecem a receber configurações de provisionamento em banda do servidor.</span><span class="sxs-lookup"><span data-stu-id="020da-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="020da-112">A tabela a seguir lista as configurações de política de grupo que estão disponíveis para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="020da-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="020da-113">Configurações da política de grupo para o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="020da-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020da-114">Configuração de Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="020da-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="020da-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="020da-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020da-116">Especificar servidor</span><span class="sxs-lookup"><span data-stu-id="020da-116">Specify Server</span></span><br />
<span data-ttu-id="020da-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="020da-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="020da-118">Especifica como o Lync 2013 identifica o transporte e o servidor a serem usados durante a entrada.</span><span class="sxs-lookup"><span data-stu-id="020da-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="020da-119">Com essa configuração, você especifica o seguinte:</span><span class="sxs-lookup"><span data-stu-id="020da-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="020da-120">ServerAddressExternal: Especifica o nome de servidor ou endereço IP utilizado pelos clientes e contatos federados ao se conectar de fora do firewall externo.</span><span class="sxs-lookup"><span data-stu-id="020da-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="020da-121">ServerAddressInternal: Especifica o nome de servidor ou endereço IP utilizado quando os clientes se conectam de dentro do firewall da organização.</span><span class="sxs-lookup"><span data-stu-id="020da-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="020da-122">Transport: Especifica o protocolo TCP ou protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="020da-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-123">Versões adicionais do servidor com suporte</span><span class="sxs-lookup"><span data-stu-id="020da-123">Additional server versions supported</span></span><br />
<span data-ttu-id="020da-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="020da-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="020da-125">Especifica uma lista de nomes de versão do servidor separados por ponto-e-vírgulas nos quais o Lync Server 2013 fará logon, além das versões do servidor com suporte por padrão.</span><span class="sxs-lookup"><span data-stu-id="020da-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-126">Desativa o upload automático de logs de falha de assinatura (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="020da-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="020da-127">Carrega automaticamente os logs de falha de entrada no Lync Server para análise.</span><span class="sxs-lookup"><span data-stu-id="020da-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="020da-128">Nenhum log será carregado automaticamente se a entrada ocorrer com êxito.</span><span class="sxs-lookup"><span data-stu-id="020da-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="020da-129">Se essa política não estiver configurada, ocorrerá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="020da-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="020da-130">Para usuários do Lync Online: logs de falha de entrada são carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="020da-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="020da-131">Para usuários do Lync local: uma caixa de diálogo de confirmação é exibida para o usuário antes do carregamento.</span><span class="sxs-lookup"><span data-stu-id="020da-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="020da-132">Quando essa configuração estiver desabilitada, os logs de entrada serão carregados automaticamente para o servidor do Lync para os usuários do Lync local e do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="020da-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="020da-133">Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="020da-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-134">Desabilitar o fallback de HTTP para conexão SIP</span><span class="sxs-lookup"><span data-stu-id="020da-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="020da-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="020da-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="020da-136">Impede que o Lync Server tente se conectar ao servidor usando HTTP, se TLS ou TCP não estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="020da-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="020da-137">Por padrão, o Lync tenta primeiro se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Lync tenta se conectar usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="020da-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="020da-138">Use essa política para desabilitar a tentativa de conexão por HTTP de fallback.</span><span class="sxs-lookup"><span data-stu-id="020da-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-139">Exigir credenciais de logon</span><span class="sxs-lookup"><span data-stu-id="020da-139">Require logon credentials</span></span><br />
<span data-ttu-id="020da-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="020da-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="020da-141">Requer que o usuário forneça credenciais de logon para o Lync em vez de usar as credenciais do Windows automaticamente durante a entrada em um servidor SIP.</span><span class="sxs-lookup"><span data-stu-id="020da-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-142">Desabilitar a verificação de versão do servidor</span><span class="sxs-lookup"><span data-stu-id="020da-142">Disable server version check</span></span><br />
<span data-ttu-id="020da-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="020da-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="020da-144">Se você definir essa política como 1, o Lync não verifica o nome e a versão do servidor antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="020da-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="020da-145">Por padrão, o Lync faz essas verificações antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="020da-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-146">Habilitar o uso do BITS para baixar arquivos do serviço de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="020da-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="020da-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="020da-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="020da-148">Permite que o Lync use o serviço de transferência inteligente em segundo plano (BITS) para baixar os arquivos dos serviços de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="020da-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-149">Configurar o modo de segurança SIP</span><span class="sxs-lookup"><span data-stu-id="020da-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="020da-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="020da-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="020da-151">Permite que o Lync envie e receba mensagens de chat com mais segurança.</span><span class="sxs-lookup"><span data-stu-id="020da-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="020da-152">Essa política não tem efeito no Windows .NET, nem em serviços de Servidor do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="020da-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="020da-153">Se você não definir essa configuração de política, o Lync poderá usar qualquer transporte.</span><span class="sxs-lookup"><span data-stu-id="020da-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="020da-154">Mas se ele não usar TLS e se o servidor autenticar usuários, o Lync deverá usar a autenticação NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="020da-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-155">Atraso inicial do download do catálogo de endereços global</span><span class="sxs-lookup"><span data-stu-id="020da-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="020da-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="020da-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="020da-p110">Especifica o período de tempo antes de um download da lista de endereço global (GAL) ocorrer. O valor padrão é 60 minutos, o que significa que o download do arquivo GAL é atrasado para um período aleatório entre 0 e 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="020da-p110">Specifies the time period before a download of the global address list (GAL) occurs. The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-159">Impedir que os usuários executem o Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="020da-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="020da-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="020da-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="020da-161">Impede que os usuários executem o Lync.</span><span class="sxs-lookup"><span data-stu-id="020da-161">Prevents users from running Lync.</span></span> <span data-ttu-id="020da-162">Você pode definir essa configuração de política na Configuração do Computador e na Configuração do Usuário, mas a configuração de política na Configuração do Computador tem precedência.</span><span class="sxs-lookup"><span data-stu-id="020da-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-163">Permitir armazenamento de senhas de usuários</span><span class="sxs-lookup"><span data-stu-id="020da-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="020da-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="020da-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="020da-165">Permite que o Lync armazene senhas.</span><span class="sxs-lookup"><span data-stu-id="020da-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-166">Configurar o modo de compactação SIP</span><span class="sxs-lookup"><span data-stu-id="020da-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="020da-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="020da-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="020da-p112">Especifica quando ativar a compressão do SIP. Por padrão, a compressão do SIP está ativada com base na velocidade do adaptador. Observe que configurar tal política pode causar um aumento no tempo de assinatura.</span><span class="sxs-lookup"><span data-stu-id="020da-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-171">Lista de domínios confiáveis</span><span class="sxs-lookup"><span data-stu-id="020da-171">Trusted Domain List</span></span><br />
<span data-ttu-id="020da-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="020da-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="020da-173">Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP cliente.</span><span class="sxs-lookup"><span data-stu-id="020da-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020da-p113">As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.</span><span class="sxs-lookup"><span data-stu-id="020da-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="020da-176">Precedência das Políticas de Grupo</span><span class="sxs-lookup"><span data-stu-id="020da-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020da-177">Precedência</span><span class="sxs-lookup"><span data-stu-id="020da-177">Precedence</span></span></th>
<th><span data-ttu-id="020da-178">Local ou método da configuração</span><span class="sxs-lookup"><span data-stu-id="020da-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020da-179">1</span><span class="sxs-lookup"><span data-stu-id="020da-179">1</span></span></p></td>
<td><p><span data-ttu-id="020da-180">Provisionamento em banda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020da-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-181">2</span><span class="sxs-lookup"><span data-stu-id="020da-181">2</span></span></p></td>
<td><p><span data-ttu-id="020da-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="020da-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020da-183">3</span><span class="sxs-lookup"><span data-stu-id="020da-183">3</span></span></p></td>
<td><p><span data-ttu-id="020da-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="020da-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020da-185">4</span><span class="sxs-lookup"><span data-stu-id="020da-185">4</span></span></p></td>
<td><p><span data-ttu-id="020da-186">A caixa de diálogo Lync-opções no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="020da-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="020da-187">Para definir configurações de política de grupo usando os arquivos de modelo administrativo do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="020da-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="020da-p114">Crie uma pasta de nível de raiz para inserir todos os arquivos ADMX de idioma neutro. Por exemplo, crie uma pasta raiz para o armazenamento central no controlador de domínio neste local:</span><span class="sxs-lookup"><span data-stu-id="020da-p114">Create a root-level folder to contain all language-neutral ADMX files. For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="020da-p115">Este procedimento presume que você deseja gerenciar diversos computadores no seu domínio. Neste caso, armazene os modelos em um repositório central na pasta Sysvol no controlador de domínio primário. Isso fornece uma localização de armazenamento central replicado para Modelos Administrativos.</span><span class="sxs-lookup"><span data-stu-id="020da-p115">This procedure assumes that you want to manage multiple computers in your domain. In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller. This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="020da-p116">Crie uma subpasta para cada idioma que for utilizar. Essas subpastas vão conter os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para United States English (EN-US) neste local:</span><span class="sxs-lookup"><span data-stu-id="020da-p116">Create a subfolder for each language that you’ll use. These subfolders will contain the language-specific ADML resource files. For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

