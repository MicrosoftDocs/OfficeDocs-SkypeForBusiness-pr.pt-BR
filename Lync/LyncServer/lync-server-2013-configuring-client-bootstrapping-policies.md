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
ms.openlocfilehash: 3827bf913c4108c1105376a6f178598a2fb45a06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="e48b5-102">Configurando políticas de inicialização do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e48b5-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e48b5-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e48b5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e48b5-104">O GPMC (console de gerenciamento de política de grupo) e o editor de objeto de diretiva de grupo são ferramentas que você usa para gerenciar a política de grupo.</span><span class="sxs-lookup"><span data-stu-id="e48b5-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="e48b5-105">Incluído no modelo administrativo da política de grupo do Office estão os modelos administrativos do Lync 2013. admx (ADMX) e. adml (ADML), que contêm as configurações de política baseadas no registro que você configura para os objetos de política de grupo no domínio.</span><span class="sxs-lookup"><span data-stu-id="e48b5-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="e48b5-106">Os arquivos ADML são complementos específicos do idioma para arquivos ADMX.</span><span class="sxs-lookup"><span data-stu-id="e48b5-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="e48b5-107">Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="e48b5-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="e48b5-108">Para obter mais informações, consulte "arquivos de modelo administrativo do Office 2013 (ADMX, ADML)" na documentação do <http://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 em.</span><span class="sxs-lookup"><span data-stu-id="e48b5-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="e48b5-109">Para o Lync 2013, há várias políticas de inicialização do cliente que devem ser consideradas configuradas antes que os usuários entrem no servidor pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="e48b5-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="e48b5-110">Por exemplo, os servidores e o modo de segurança padrão que o cliente deve usar até que o logon seja concluído.</span><span class="sxs-lookup"><span data-stu-id="e48b5-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="e48b5-111">Você pode usar a política de grupo para estabelecer essas configurações nos registros de computador dos usuários antes de entrar e começar a receber as configurações de provisionamento em banda no servidor.</span><span class="sxs-lookup"><span data-stu-id="e48b5-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="e48b5-112">A tabela a seguir lista as configurações de política de grupo disponíveis para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e48b5-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="e48b5-113">Configurações da política de grupo para o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e48b5-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e48b5-114">Configuração da Política de grupo</span><span class="sxs-lookup"><span data-stu-id="e48b5-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="e48b5-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e48b5-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-116">Especificar servidor</span><span class="sxs-lookup"><span data-stu-id="e48b5-116">Specify Server</span></span><br />
<span data-ttu-id="e48b5-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="e48b5-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-118">Especifica como o Lync 2013 identifica o transporte e o servidor a serem usados durante a entrada.</span><span class="sxs-lookup"><span data-stu-id="e48b5-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="e48b5-119">Nesta configuração, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e48b5-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48b5-120">ServerAddressExternal: especifica o nome do servidor ou endereço IP usado por clientes e contatos federados ao se conectar de fora do firewall externo.</span><span class="sxs-lookup"><span data-stu-id="e48b5-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="e48b5-121">ServerAddressInternal: especifica o nome do servidor ou endereço IP usado quando os clientes se conectam de dentro do firewall da organização.</span><span class="sxs-lookup"><span data-stu-id="e48b5-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="e48b5-122">Transport: especifica o protocolo de controle de transmissão (TCP) ou TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="e48b5-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-123">Versões de servidor adicionais suportadas</span><span class="sxs-lookup"><span data-stu-id="e48b5-123">Additional server versions supported</span></span><br />
<span data-ttu-id="e48b5-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="e48b5-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-125">Especifica uma lista de nomes de versão de servidor separados por ponto e vírgula nos quais o Lync Server 2013 fará logon, além das versões de servidor que têm suporte por padrão.</span><span class="sxs-lookup"><span data-stu-id="e48b5-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-126">Desabilitar o carregamento automático de logs de falha de entrada (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="e48b5-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-127">Carrega automaticamente os logs de falha de entrada no Lync Server para análise.</span><span class="sxs-lookup"><span data-stu-id="e48b5-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="e48b5-128">Nenhum log será carregado automaticamente se a conexão for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="e48b5-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="e48b5-129">Se essa política não estiver configurada, ocorrerá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e48b5-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e48b5-130">Para usuários do Lync Online: logs de falha de entrada são carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e48b5-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e48b5-131">Para usuários locais do Lync: uma caixa de diálogo de confirmação é exibida para o usuário antes do carregamento.</span><span class="sxs-lookup"><span data-stu-id="e48b5-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="e48b5-132">Quando essa configuração é desabilitada, os logs de entrada são carregados automaticamente no Lync Server para os usuários do Lync local e do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e48b5-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="e48b5-133">Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e48b5-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-134">Desabilitar fallback de HTTP para conexão SIP</span><span class="sxs-lookup"><span data-stu-id="e48b5-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="e48b5-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="e48b5-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-136">Impede que o Lync Server tente se conectar ao servidor usando HTTP, se TLS ou TCP não estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e48b5-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="e48b5-137">Por padrão, o Lync primeiro tenta se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Lync tentará se conectar usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="e48b5-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="e48b5-138">Use essa política para desabilitar a tentativa de conexão HTTP de fallback.</span><span class="sxs-lookup"><span data-stu-id="e48b5-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-139">Exigir credenciais de logon</span><span class="sxs-lookup"><span data-stu-id="e48b5-139">Require logon credentials</span></span><br />
<span data-ttu-id="e48b5-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="e48b5-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-141">Requer que o usuário forneça credenciais de logon para o Lync em vez de usar automaticamente as credenciais do Windows durante a entrada em um servidor SIP.</span><span class="sxs-lookup"><span data-stu-id="e48b5-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-142">Desabilitar verificação de versão do servidor</span><span class="sxs-lookup"><span data-stu-id="e48b5-142">Disable server version check</span></span><br />
<span data-ttu-id="e48b5-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="e48b5-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-144">Se você definir essa política como 1, o Lync não poderá verificar o nome e a versão do servidor antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="e48b5-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="e48b5-145">Por padrão, o Lync faz essas verificações antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="e48b5-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-146">Habilitar o uso de BITS para baixar arquivos do serviço de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="e48b5-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="e48b5-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="e48b5-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-148">Permite que o Lync use o serviço de transferência inteligente em segundo plano (BITS) para baixar os arquivos dos serviços de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="e48b5-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-149">Configurar o modo de segurança SIP</span><span class="sxs-lookup"><span data-stu-id="e48b5-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="e48b5-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="e48b5-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-151">Permite que o Lync envie e receba mensagens instantâneas com mais segurança.</span><span class="sxs-lookup"><span data-stu-id="e48b5-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="e48b5-152">Essa política não tem efeito sobre os serviços .NET ou Microsoft Exchange Server do Windows.</span><span class="sxs-lookup"><span data-stu-id="e48b5-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="e48b5-153">Se você não definir essa configuração de política, o Lync poderá usar qualquer transporte.</span><span class="sxs-lookup"><span data-stu-id="e48b5-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="e48b5-154">Mas se ele não usar TLS e se o servidor autenticar usuários, o Lync deverá usar a autenticação NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e48b5-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-155">Atraso inicial de download do catálogo de endereços global</span><span class="sxs-lookup"><span data-stu-id="e48b5-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="e48b5-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="e48b5-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-157">Especifica o período de tempo antes da ocorrência de um download da GAL (lista de endereços global).</span><span class="sxs-lookup"><span data-stu-id="e48b5-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="e48b5-158">O valor padrão é 60 minutos, o que significa que o servidor atrasa o download do arquivo GAL por um período aleatório entre 0 e 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="e48b5-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-159">Impedir que os usuários executem o Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="e48b5-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="e48b5-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="e48b5-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-161">Impede que os usuários executem o Lync.</span><span class="sxs-lookup"><span data-stu-id="e48b5-161">Prevents users from running Lync.</span></span> <span data-ttu-id="e48b5-162">Você pode configurar essa definição de diretiva em Configuração do Computador e em Configuração do Usuário, mas a definição de Configuração do Computador tem precedência.</span><span class="sxs-lookup"><span data-stu-id="e48b5-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-163">Permitir o armazenamento de senhas de usuário</span><span class="sxs-lookup"><span data-stu-id="e48b5-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="e48b5-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="e48b5-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-165">Permite que o Lync armazene senhas.</span><span class="sxs-lookup"><span data-stu-id="e48b5-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-166">Configurar o modo de compactação SIP</span><span class="sxs-lookup"><span data-stu-id="e48b5-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="e48b5-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="e48b5-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-168">Especifica quando ativar a compactação SIP.</span><span class="sxs-lookup"><span data-stu-id="e48b5-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="e48b5-169">Por padrão, a compactação SIP é ativada com base na velocidade do adaptador.</span><span class="sxs-lookup"><span data-stu-id="e48b5-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="e48b5-170">Observe que a configuração dessa política pode causar um aumento no tempo de login.</span><span class="sxs-lookup"><span data-stu-id="e48b5-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-171">Lista de domínios confiáveis</span><span class="sxs-lookup"><span data-stu-id="e48b5-171">Trusted Domain List</span></span><br />
<span data-ttu-id="e48b5-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="e48b5-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="e48b5-173">Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP do cliente.</span><span class="sxs-lookup"><span data-stu-id="e48b5-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e48b5-p113">As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.</span><span class="sxs-lookup"><span data-stu-id="e48b5-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="e48b5-176">Precedência das Políticas de Grupo</span><span class="sxs-lookup"><span data-stu-id="e48b5-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e48b5-177">Precedence</span><span class="sxs-lookup"><span data-stu-id="e48b5-177">Precedence</span></span></th>
<th><span data-ttu-id="e48b5-178">Local ou método da configuração</span><span class="sxs-lookup"><span data-stu-id="e48b5-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-179">1 </span><span class="sxs-lookup"><span data-stu-id="e48b5-179">1</span></span></p></td>
<td><p><span data-ttu-id="e48b5-180">Provisionamento em banda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e48b5-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-181">2 </span><span class="sxs-lookup"><span data-stu-id="e48b5-181">2</span></span></p></td>
<td><p><span data-ttu-id="e48b5-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="e48b5-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48b5-183">3 </span><span class="sxs-lookup"><span data-stu-id="e48b5-183">3</span></span></p></td>
<td><p><span data-ttu-id="e48b5-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="e48b5-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48b5-185">4 </span><span class="sxs-lookup"><span data-stu-id="e48b5-185">4</span></span></p></td>
<td><p><span data-ttu-id="e48b5-186">A caixa de diálogo Lync-Options no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e48b5-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="e48b5-187">Para definir as configurações de política de grupo usando os arquivos de modelo administrativo do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e48b5-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="e48b5-188">Crie uma pasta de nível de raiz para que contenha todos os arquivos ADMX de idioma neutro.</span><span class="sxs-lookup"><span data-stu-id="e48b5-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="e48b5-189">Por exemplo, crie a pasta raiz do repositório central em seu controlador de domínio neste local:</span><span class="sxs-lookup"><span data-stu-id="e48b5-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e48b5-190">Este procedimento pressupõe que você deseja gerenciar vários computadores em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e48b5-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="e48b5-191">Nesse caso, você armazena os modelos em um repositório central na pasta SYSVOL no controlador de domínio primário.</span><span class="sxs-lookup"><span data-stu-id="e48b5-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="e48b5-192">Isso oferece um local de repositório central para Modelos Administrativos do domínio.</span><span class="sxs-lookup"><span data-stu-id="e48b5-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="e48b5-193">Crie uma subpasta para cada idioma que você usará.</span><span class="sxs-lookup"><span data-stu-id="e48b5-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="e48b5-194">Essas subpastas conterão os arquivos de recurso ADML específicos do idioma.</span><span class="sxs-lookup"><span data-stu-id="e48b5-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="e48b5-195">Por exemplo, crie uma subpasta para o inglês dos Estados Unidos (EN-US) neste local:</span><span class="sxs-lookup"><span data-stu-id="e48b5-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

