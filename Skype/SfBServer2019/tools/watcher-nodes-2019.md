---
title: Configurar os computadores do Skype for Business Server que serão monitorados
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Instale os arquivos do agente do Operations Manager no computador do Skype for Business Server 2019 a ser monitorado e configure o computador para atuar como um proxy do System Center.'
ms.openlocfilehash: 062dfeb4b03cbe68de21bcb4ea8722bf0f666070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150482"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="da5e7-103">Configurar os computadores do Skype for Business Server que serão monitorados</span><span class="sxs-lookup"><span data-stu-id="da5e7-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="da5e7-104">**Resumo:** Instale os arquivos do agente do Operations Manager no computador do Skype for Business Server 2019 a ser monitorado e configure o computador para atuar como um proxy do System Center.</span><span class="sxs-lookup"><span data-stu-id="da5e7-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="da5e7-105">Cada computador do Skype for Business Server 2019 que você deseja monitorar deve ser capaz de autorelatar sua existência ao servidor de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="da5e7-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="da5e7-106">Para habilitar esse processo, você deve instalar os arquivos do agente do Operations Manager em cada um dos computadores a serem monitorados.</span><span class="sxs-lookup"><span data-stu-id="da5e7-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="da5e7-107">Após instalar os arquivos de agente, você deve configurar o computador para atuar como um proxy do System Center.</span><span class="sxs-lookup"><span data-stu-id="da5e7-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="da5e7-108">Certifique-se de que você instalou e configurou o Skype for Business Server pela primeira vez nesses computadores antes de executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="da5e7-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="da5e7-109">Instalando um Certificado no Nó Inspetor Localizado Fora da Rede do Perímetro</span><span class="sxs-lookup"><span data-stu-id="da5e7-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="da5e7-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="da5e7-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="da5e7-111">Os agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Skype for Business Server), fora da empresa (como um nó do Inspetor de transação sintético externo) ou em um limite de confiança do Active Directory, podem exigir a configuração de um servidor de gateway do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5e7-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="da5e7-112">Essa função de servidor habilita agentes que não têm uma relação de confiança com o servidor de gerenciamento raiz para gerar alertas.</span><span class="sxs-lookup"><span data-stu-id="da5e7-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="da5e7-113">Para obter detalhes, consulte [Managing gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span><span class="sxs-lookup"><span data-stu-id="da5e7-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span></span>

<span data-ttu-id="da5e7-114">Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5e7-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="da5e7-115">Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher.</span><span class="sxs-lookup"><span data-stu-id="da5e7-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="da5e7-116">Para obter detalhes e baixar esses utilitários, consulte [obtendo certificados para agentes não associados ao domínio simplificados com o assistente de geração de certificados](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="da5e7-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="da5e7-117">Instalando os arquivos do agente do Operation Manager</span><span class="sxs-lookup"><span data-stu-id="da5e7-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="da5e7-118">Na mídia de instalação do System Center, clique duas vezes em **Setup. exe**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="da5e7-119">No assistente de instalação do System Center Operation Manager, clique em **instalar o agente do Operations Manager**, em instalar agente em instalações opcionais</span><span class="sxs-lookup"><span data-stu-id="da5e7-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="da5e7-120">No assistente de configuração do System Center, na página Bem-vindo ao assistente de instalação do System Center Operations Manager, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="da5e7-121">Na página pasta de destino, selecione a pasta onde os arquivos do agente do Operations Manager serão instalados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="da5e7-122">Na página configuração do grupo de gerenciamento, selecione **especificar informações do grupo de gerenciamento** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="da5e7-123">Na página configuração do grupo de gerenciamento, digite o nome do grupo de gerenciamento do Operations Manager na caixa **nome do grupo de gerenciamento** e, em seguida, digite o nome do host do seu servidor do Operations Manager (por exemplo, ATL-SCOM-001) na caixa servidor de **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="da5e7-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="da5e7-124">Se você alterou o número da porta usada pelo Operations Manager, insira o novo número da porta na caixa **porta do servidor de gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="da5e7-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="da5e7-125">Caso contrário, deixe a porta no valor padrão de 5723 e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="da5e7-126">Na página conta de ação do agente, selecione **sistema local** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="da5e7-127">Na página Microsoft Update, selecione **eu não desejo usar o Microsoft Update** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="da5e7-128">Na página Pronto para Instalar, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="da5e7-129">Na página Concluindo o assistente de instalação do System Center Operations Manager, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="da5e7-130">Clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-130">Click **Exit**.</span></span>

<span data-ttu-id="da5e7-131">Para o System Center 2012, você pode verificar se o agente foi criado clicando em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2012**e, em seguida, em **operações do Shell de gerenciamento do 2012**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="da5e7-132">No Shell do Operations Manager, digite o seguinte comando do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="da5e7-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="da5e7-133">Será exibida uma lista de todos os seus agentes do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5e7-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="da5e7-134">Configurando o computador do Skype for Business Server para participar da descoberta do System Center</span><span class="sxs-lookup"><span data-stu-id="da5e7-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="da5e7-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="da5e7-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="da5e7-136">Para certificar-se de que seu novo agente do Skype for Business Server participa do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador em que o console do System Center Operations Manager tenha sido instalado:</span><span class="sxs-lookup"><span data-stu-id="da5e7-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="da5e7-137">Na guia Administração, clique em **Agente Gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="da5e7-138">Clique no **Assistente de descoberta** e conclua o assistente para que o computador seja descoberto.</span><span class="sxs-lookup"><span data-stu-id="da5e7-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="da5e7-139">Reinicialize o serviço do agente de integridade.</span><span class="sxs-lookup"><span data-stu-id="da5e7-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="da5e7-140">A reinicialização do serviço forçará a descoberta do novo computador.</span><span class="sxs-lookup"><span data-stu-id="da5e7-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="da5e7-141">Se você não reiniciar o serviço, pode levar até 4 horas antes da nova máquina ser descoberta pelo System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5e7-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="da5e7-142">Verifique se nenhum evento de erro foi registrado no log de eventos do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5e7-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="da5e7-143">O computador em que o agente é enviado com êxito será mostrado na lista "gerenciado por agente" e o computador onde o agente foi instalado manualmente será mostrado em "gerenciamento pendente", clique no nome do computador e aprove.</span><span class="sxs-lookup"><span data-stu-id="da5e7-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="da5e7-144">Clique com o botão direito no nome do computador e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="da5e7-145">Na caixa de diálogo Propriedades, na guia Segurança, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="da5e7-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


