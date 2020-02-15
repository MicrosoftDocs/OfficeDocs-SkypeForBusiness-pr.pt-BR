---
title: 'Lync Server 2013: instalar os arquivos para o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7549d5efad333038dd6633c0c74192b3293933ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="2c46b-102">Instalar os arquivos para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c46b-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c46b-103">_**Última modificação do tópico:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="2c46b-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="2c46b-104">Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="2c46b-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="2c46b-105">Use as etapas deste tópico para executar o assistente de implantação do Lync Server 2013 para instalar os arquivos do servidor de mediação em um computador adicionado a um pool do servidor de mediação quando você usou o construtor de topologias para definir e publicar o pool.</span><span class="sxs-lookup"><span data-stu-id="2c46b-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="2c46b-106">Ao instalar o servidor de mediação de arquivos, você também instala e atribui o certificado exigido por cada computador em um pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2c46b-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="2c46b-107">Neste site, se você já implantou servidores de mediação colocados no pool de front-ends ou no servidor Standard Edition, pode ignorar este tópico e, em vez disso, continuar a [Configurar troncos no Lync server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="2c46b-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c46b-108">Este tópico pressupõe que você já tenha definido e publicado um pool do servidor de mediação autônomo, conforme descrito em <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir um servidor de mediação no construtor de topologias no Lync Server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação de implantação e que você verificou que os computadores no pool do servidor de mediação atendem aos pré-requisitos descritos nos <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">pré-requisitos de software para o enterprise Voice no Lync Server 2013</A> e os <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">pré-requisitos de segurança e configuração para empresas Voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c46b-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="2c46b-109">Para instalar os arquivos em um pool do Servidor de Mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="2c46b-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="2c46b-110">Na mídia de instalação, clique com o \<botão direito\>em instalação de instalação de mídia**\\\\\\AMD64. exe**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="2c46b-111">Na página **Local de instalação**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="2c46b-p102">Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)</span><span class="sxs-lookup"><span data-stu-id="2c46b-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="2c46b-114">Na página **Assistente de Implantação do Lync Server 2010**, clique em **Instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="2c46b-115">Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="2c46b-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="2c46b-116">Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="2c46b-117">Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="2c46b-118">Próximo a **Etapa 2: Configurar ou remover os componentes do Lync Server**, clique em **Executar** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="2c46b-119">Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="2c46b-p103">Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribui-lo.</span><span class="sxs-lookup"><span data-stu-id="2c46b-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="2c46b-123">Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="2c46b-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="2c46b-124">Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="2c46b-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="2c46b-125">No computador em que você está executando o painel de controle do Lync Server, verifique na página **topologia** do painel de controle do Lync Server que o status do serviço do servidor de mediação é mostrado como uma marca de seleção verde.</span><span class="sxs-lookup"><span data-stu-id="2c46b-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="2c46b-126">Se um X vermelho é exibido, selecione o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="2c46b-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="2c46b-127">No menu **Ações**, clique em **Iniciar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="2c46b-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="2c46b-128">Se você tiver adicionado mais de um computador ao pool do servidor de mediação, execute as etapas neste procedimento em todos os outros computadores no pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2c46b-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="2c46b-129">Se você não precisar instalar arquivos para o servidor de mediação para qualquer outro computador, siga os procedimentos em [Configurando troncos no Lync server 2013](lync-server-2013-configuring-trunks.md) para definir as configurações para a conexão de tronco entre este pool de servidor de mediação (ou todos os servidores de mediação em um site) e seu par.</span><span class="sxs-lookup"><span data-stu-id="2c46b-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c46b-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c46b-130">See Also</span></span>


[<span data-ttu-id="2c46b-131">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c46b-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

