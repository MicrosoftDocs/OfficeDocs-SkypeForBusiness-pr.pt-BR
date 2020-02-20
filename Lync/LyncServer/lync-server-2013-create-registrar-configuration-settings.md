---
title: 'Lync Server 2013: criar definições de configuração do registrador'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6167e82679aa0124b2ae8833be9d4a9a56df2009
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8cbcd-102">Criar definições de configuração do registrador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cbcd-103">_**Última modificação do tópico:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="8cbcd-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="8cbcd-p101">É possível usar o Registrador para configurar métodos de autenticação do servidor proxy. O protocolo de autenticação que você especificar determina que tipo de desafios os servidores no pool vão gerar para os clientes. Os protocolos disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="8cbcd-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="8cbcd-107">**Kerberos**   este é o esquema de autenticação de senha mais seguro disponível para clientes, mas normalmente está disponível somente para clientes corporativos, pois requer conexão do cliente com um centro de distribuição de chaves (controlador de domínio Kerberos).</span><span class="sxs-lookup"><span data-stu-id="8cbcd-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="8cbcd-108">Essa configuração é apropriada se o servidor autenticar somente clientes empresariais.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="8cbcd-109">**NTLM**   esta é a autenticação baseada em senha disponível para clientes que usam um esquema de hash de resposta de desafio na senha.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="8cbcd-110">Essa é a única forma de autenticação disponível para clientes sem conectividade com um Centro de distribuição de chaves (controlador de domínio Kerberos), como usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="8cbcd-111">Se um servidor autenticar somente usuários remotos, escolha NTLM.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="8cbcd-112">**Autenticação de certificado**   esse é o novo método de autenticação quando o servidor precisa obter certificados de clientes do Lync Phone Edition, telefones de área comum, Lync 2013 e o aplicativo Lync da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="8cbcd-113">Nos clientes do Lync Phone Edition, depois que um usuário entra e é autenticado com êxito, fornecendo um PIN (número de identificação pessoal), o Lync Server 2013 e, em seguida, provisiona o URI do SIP para o telefone e fornece um certificado assinado do Lync Server ou um certificado de usuário que identifica Joe (ex: SN=joe@contoso.com) para o telefone.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="8cbcd-114">Esse certificado é usado para autenticação com o Registrador e Serviços Web.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8cbcd-p105">Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="8cbcd-119">Se você usar os clientes do aplicativo Lync da Windows Store, deverá habilitar a autenticação de certificado.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="8cbcd-120">Execute estas etapas para criar um novo Registrador.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="8cbcd-121">Para criar novas definições de configuração do registrador</span><span class="sxs-lookup"><span data-stu-id="8cbcd-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="8cbcd-122">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8cbcd-123">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8cbcd-124">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8cbcd-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8cbcd-125">Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="8cbcd-126">Na página **Registrador**, clique em **Novo**</span><span class="sxs-lookup"><span data-stu-id="8cbcd-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="8cbcd-127">Em \*\*Selecionar um Serviço \*\*, clique no serviço ao qual o Registrador será aplicado e clique em \*\*OK \*\*.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="8cbcd-128">Em \*\*Nova Configuração do Registrador \*\*, selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes e do suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="8cbcd-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="8cbcd-129">**Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="8cbcd-130">**Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="8cbcd-131">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="8cbcd-132">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

