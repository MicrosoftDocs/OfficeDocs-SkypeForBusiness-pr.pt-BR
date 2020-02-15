---
title: Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ef6082c4d2df6936557cf6f6c82a1d495888f55
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="252a4-102">Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="252a4-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="252a4-103">_**Última modificação do tópico:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="252a4-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="252a4-104">O Microsoft Lync Server 2013 suporta o uso de uma porta não padrão e um alias no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="252a4-105">Usar uma porta não padrão do SQL Server e um alias aumenta a segurança e cria um ambiente mais flexível para a implantação do Lync.</span><span class="sxs-lookup"><span data-stu-id="252a4-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="252a4-106">Estas etapas são apenas uma única etapa de proteção adequada do seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="252a4-107">Etapas adicionais devem ser seguidas para reduzir a superfície de ataque de uma implementação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="252a4-108">O artigo a seguir descreve as etapas necessárias para configurar uma porta não padrão do SQL Server e alias no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="252a4-109">Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="252a4-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="252a4-110">O construtor de topologias do Lync Server 2013 suporta o uso de um alias do SQL Server como o FQDN (nome de domínio totalmente qualificado) em vez do FQDN do SQL Server atual ao configurar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="252a4-111">Isso permite que o FQDN do SQL Server real fique oculto de qualquer invasor mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="252a4-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="252a4-112">Além disso, o uso de uma porta não-padrão obscurece a porta real de qualquer invasor que esteja tentando atacar o banco de dados na porta 1433 padrão, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="252a4-113">![Um hacker não sabe o número da porta a ser atacado.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Um hacker não sabe o número da porta a ser atacado.")</span><span class="sxs-lookup"><span data-stu-id="252a4-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="252a4-114">Para ter êxito ao determinar que a porta que o Lync Server 2013 está usando para se comunicar com o SQL Server, o invasor precisaria verificar todas as portas para obter as informações de porta.</span><span class="sxs-lookup"><span data-stu-id="252a4-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="252a4-115">Uma verificação de porta por um invasor aumenta as chances de que a segurança possa detectar e interromper a instrução.</span><span class="sxs-lookup"><span data-stu-id="252a4-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="252a4-116">Além de adicionar maior segurança a uma porta não padrão, você também pode usar um alias do SQL Server para oferecer flexibilidade para a implantação.</span><span class="sxs-lookup"><span data-stu-id="252a4-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="252a4-117">Isso é útil para reduzir as alterações de configuração em situações em que é necessário alterar o nome do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="252a4-118">O SQL Server fornece dois métodos de tolerância a falhas (clustering de failover e espelhamento).</span><span class="sxs-lookup"><span data-stu-id="252a4-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="252a4-119">Os métodos de tolerância a falhas do SQL Server têm suporte usando uma porta não padrão do SQL Server e alias com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="252a4-120">Se o back-end do SQL Server usado pelo pool estiver em uma configuração espelhada, então o SQL browser Service nos servidores backend do SQL Server deverá estar em execução para que os servidores front-end se conectem ao banco de dados espelhado quando os bancos de dados tiverem failover para o SQL espelhado Do.</span><span class="sxs-lookup"><span data-stu-id="252a4-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="252a4-121">Ao configurar a conectividade de banco de dados do SQL Server a partir do construtor de topologias, ou ao usar o cmdlet Install-CsDatabase, não é possível definir explicitamente um número de porta não padrão do SQL Server e associá-lo a uma instância SQL.</span><span class="sxs-lookup"><span data-stu-id="252a4-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="252a4-122">Para definir uma porta não padrão, você precisará usar os utilitários do SQL Server e do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="252a4-123">Para configurar uma porta e um alias não padrão do SQL Server para uso com o Lync Server 2013, será necessário concluir três etapas principais.</span><span class="sxs-lookup"><span data-stu-id="252a4-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="252a4-124">Essas etapas são:</span><span class="sxs-lookup"><span data-stu-id="252a4-124">These steps are:</span></span>

  - <span data-ttu-id="252a4-125">Confirme se o Lync Server 2013 tem as atualizações mais recentes aplicadas.</span><span class="sxs-lookup"><span data-stu-id="252a4-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="252a4-126">Configure a porta e o alias não padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="252a4-127">Configure o Lync Server 2013 com o alias do SQL Server usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="252a4-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="252a4-128">Publique a topologia e verifique o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="252a4-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="252a4-129">Confirmar se o Lync Server 2013 tem as atualizações mais recentes aplicadas</span><span class="sxs-lookup"><span data-stu-id="252a4-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="252a4-130">É importante manter atualizado o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="252a4-131">Para verificar as atualizações e informações mais recentes sobre como aplicá-las, consulte [atualizações para o Lync Server 2013](http://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="252a4-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="252a4-132">Configurar a porta e o alias não padrão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="252a4-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="252a4-133">A porta e o alias não padrão do SQL Server devem ser configurados na instância do banco de dados antes de ser referenciado do construtor de topologias do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="252a4-134">Para configurar uma porta e um alias não padrão do SQL Server, você precisará concluir três etapas principais.</span><span class="sxs-lookup"><span data-stu-id="252a4-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="252a4-135">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="252a4-135">These steps are as follows:</span></span>

  - <span data-ttu-id="252a4-136">Altere os valores de protocolo TCP/IP padrão.</span><span class="sxs-lookup"><span data-stu-id="252a4-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="252a4-137">Criar e configurar um alias do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="252a4-138">Criar um registro de recurso de nome canônico (CNAME) do sistema de nome de domínio (DNS).</span><span class="sxs-lookup"><span data-stu-id="252a4-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="252a4-139">**Modificar os valores de protocolo TCP/IP padrão**</span><span class="sxs-lookup"><span data-stu-id="252a4-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="252a4-140">Selecione **Iniciar**e escolha **Gerenciador de configuração do SQL Server**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-141">![O ícone do SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "O ícone do SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="252a4-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="252a4-142">No painel de navegação, escolha expandir a **instância do SQL Server**, optar por expandir a **configuração de rede do SQL Server**e escolher **protocolos para\>nome de \<instância**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-143">![Navegar para propriedades de TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navegar para propriedades de TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="252a4-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="252a4-144">No painel direito, clique com o botão direito do mouse em **TCP/IP**e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="252a4-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="252a4-145">A caixa de diálogo Propriedades de TCP/IP é exibida.</span><span class="sxs-lookup"><span data-stu-id="252a4-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="252a4-146">Selecione a guia **endereços IP** . A guia endereços IP mostra todos os endereços IP ativos no servidor.</span><span class="sxs-lookup"><span data-stu-id="252a4-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="252a4-147">Eles estão no formato IP1, IP2, até IPAll, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-148">![Abra as propriedades de TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Abra as propriedades de TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="252a4-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="252a4-149">Desmarque o campo **portas dinâmicas TCP** para todos os endereços IP.</span><span class="sxs-lookup"><span data-stu-id="252a4-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="252a4-150">Se o campo contiver um caractere zero, significa que o SQL Server está escutando nas portas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="252a4-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="252a4-151">Certifique-se de que esses campos estejam desmarcados e não contenham zero.</span><span class="sxs-lookup"><span data-stu-id="252a4-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="252a4-152">Para o endereço IP que o Lync Server usará para se conectar ao banco de dados, verifique se **habilitado** está definido como **Sim**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-153">![Defina habilitado como Sim para o IP correto.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Defina habilitado como Sim para o IP correto.")</span><span class="sxs-lookup"><span data-stu-id="252a4-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="252a4-154">Na seção **IPAll** na parte inferior da caixa de diálogo, digite a porta desejada no campo **porta TCP** , conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="252a4-155">Neste exemplo, usamos a porta 50062, mas você pode usar qualquer porta entre 49152 e 65535.</span><span class="sxs-lookup"><span data-stu-id="252a4-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="252a4-156">Estas são as portas atribuídas ao uso dinâmico e privado, e isso garante que você não entre em conflito com outras portas que estão sendo usadas na implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="252a4-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="252a4-157">![Set port na seção IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port na seção IPAll.")</span><span class="sxs-lookup"><span data-stu-id="252a4-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="252a4-158">Escolha **OK** para sair da caixa de diálogo Propriedades de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="252a4-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="252a4-159">Reinicie a instância do SQL Server selecionando **Serviços do SQL Server** no painel esquerdo do SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="252a4-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="252a4-160">Em seguida, clique com o botão direito do mouse no **nome \<\> da instância do SQL Server** no painel direito e selecione **reiniciar**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-161">![Redefina o serviço do SQL Server para a instância.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Redefina o serviço do SQL Server para a instância.")</span><span class="sxs-lookup"><span data-stu-id="252a4-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="252a4-162">Certifique-se de atualizar suas configurações de firewall para acomodar a nova porta do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="252a4-163">**Criar e configurar um alias do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="252a4-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="252a4-164">Selecione **Iniciar**e escolha **Gerenciador de configuração do SQL Server**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-165">![O ícone do SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "O ícone do SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="252a4-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="252a4-166">No painel esquerdo, escolha para expandir a **instância do SQL Server**, opte por expandir a **configuração \<da\> versão do SQL Native Client**e, em seguida, escolha **aliases**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-167">![Aliases no SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases no SQL Server Configuration Manager.")</span><span class="sxs-lookup"><span data-stu-id="252a4-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="252a4-168">Clique com o botão direito do mouse em **aliases**e selecione **novo alias...**.</span><span class="sxs-lookup"><span data-stu-id="252a4-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="252a4-169">Insira o **nome do alias**, o **número da porta**, o **protocolo**e o **servidor**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-170">![Criar um novo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Criar um novo alias")</span><span class="sxs-lookup"><span data-stu-id="252a4-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="252a4-171">Certifique-se de inserir a mesma porta não padrão que você usou na etapa anterior, pois esta é a porta que o SQL Server estará escutando.</span><span class="sxs-lookup"><span data-stu-id="252a4-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="252a4-172">Se um alias configurado estiver se conectando ao FQDN do SQL Server ou à instância errada, desabilite e ative novamente o protocolo de rede associado.</span><span class="sxs-lookup"><span data-stu-id="252a4-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="252a4-173">Isso limpa todas as informações de conexão armazenadas em cache e permite que o cliente se conecte corretamente.</span><span class="sxs-lookup"><span data-stu-id="252a4-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="252a4-174">**Criar um registro de recurso CNAME de DNS**</span><span class="sxs-lookup"><span data-stu-id="252a4-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="252a4-175">Entre no computador Gerenciando o DNS.</span><span class="sxs-lookup"><span data-stu-id="252a4-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="252a4-176">Selecione **Iniciar**e escolha **Gerenciador do servidor**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-177">![Abrir o Gerenciador do servidor](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Abrir o Gerenciador do servidor")</span><span class="sxs-lookup"><span data-stu-id="252a4-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="252a4-178">Escolha as **ferramentas** suspensas e selecione **DNS**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-179">![Abrir o DNS no Gerenciador do servidor.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abrir o DNS no Gerenciador do servidor.")</span><span class="sxs-lookup"><span data-stu-id="252a4-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="252a4-180">No painel esquerdo, expanda o nó nome do servidor, expanda o nó zonas de pesquisa direta e escolha o domínio relevante.</span><span class="sxs-lookup"><span data-stu-id="252a4-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="252a4-181">Clique com o botão direito do mouse no domínio e selecione **novo alias (CNAME)...**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-182">![Selecionar a opção para criar um novo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecionar a opção para criar um novo alias CNAME")</span><span class="sxs-lookup"><span data-stu-id="252a4-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="252a4-183">Insira o **nome do alias** e o **FQDN do SQL Server**, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-184">![Preenchendo a caixa de diálogo novo alias CNAME.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Preenchendo a caixa de diálogo novo alias CNAME.")</span><span class="sxs-lookup"><span data-stu-id="252a4-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="252a4-185">Escolha **OK** para salvar o CNAME e exibi-lo no Gerenciador de DNS.</span><span class="sxs-lookup"><span data-stu-id="252a4-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="252a4-186">Validar conectividade de banco de dados</span><span class="sxs-lookup"><span data-stu-id="252a4-186">Validate Database Connectivity</span></span>

<span data-ttu-id="252a4-187">Há várias maneiras diferentes de se certificar de que ele está funcionando.</span><span class="sxs-lookup"><span data-stu-id="252a4-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="252a4-188">Você deseja certificar-se de que o banco de dados do SQL Server está escutando na porta especificada usando o alias.</span><span class="sxs-lookup"><span data-stu-id="252a4-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="252a4-189">Uma verificação rápida pode ser concluída usando os comandos **netstat** e **Telnet** .</span><span class="sxs-lookup"><span data-stu-id="252a4-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="252a4-190">O cliente Telnet é um recurso que acompanha o Windows Server, mas que deve ser instalado.</span><span class="sxs-lookup"><span data-stu-id="252a4-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="252a4-191">Um recurso do Windows Server pode ser instalado ao abrir o Gerenciador do servidor e selecionar Adicionar funções e recursos no menu gerenciar.</span><span class="sxs-lookup"><span data-stu-id="252a4-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="252a4-192">**Usar netstat e Telnet para verificar a conectividade do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="252a4-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="252a4-193">Selecione **Iniciar**e digite **cmd** para abrir um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="252a4-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="252a4-194">Digite **netstat-a-f**e confirme se o SQL Server está sendo executado com a porta correta, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="252a4-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="252a4-195">![Usando netstat para verificar Port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Usando netstat para verificar Port.")</span><span class="sxs-lookup"><span data-stu-id="252a4-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="252a4-196">Digite **porta \< \# de nome\> \<de alias Telnet** para confirmar a conexão com a instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="252a4-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="252a4-197">Se a conexão for bem-sucedida, o telnet será conectado e você não verá um erro.</span><span class="sxs-lookup"><span data-stu-id="252a4-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="252a4-198">Isso mostra que a instância do SQL Server está escutando na porta correta com o alias correto.</span><span class="sxs-lookup"><span data-stu-id="252a4-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="252a4-199">Se houver um problema de conexão com o banco de dados do SQL Server, o Telnet mostrará um erro informando que a conexão não pode ser feita.</span><span class="sxs-lookup"><span data-stu-id="252a4-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="252a4-200">Agora que você verificou a conectividade do banco de dados no servidor de banco de dados, é possível fazer o mesmo com o Lync Server (pela rede) e verificar se não há firewalls bloqueando o acesso ao longo do caminho.</span><span class="sxs-lookup"><span data-stu-id="252a4-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="252a4-201">Conclusão</span><span class="sxs-lookup"><span data-stu-id="252a4-201">Conclusion</span></span>

<span data-ttu-id="252a4-202">Depois que o alias do SQL Server tiver sido configurado, você poderá usá-lo para criar uma topologia do Lync Server 2013 na ferramenta Construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="252a4-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="252a4-203">Para obter mais informações sobre topologias, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="252a4-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="252a4-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="252a4-204">See Also</span></span>


<span data-ttu-id="252a4-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planejando a segurança no Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="252a4-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="252a4-206">Definindo e configurando a topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="252a4-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="252a4-207">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="252a4-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

