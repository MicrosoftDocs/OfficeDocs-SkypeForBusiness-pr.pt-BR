---
title: Instalar os arquivos do servidor de mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumo: saiba como instalar os arquivos do servidor de mediação no Skype for Business Server.'
ms.openlocfilehash: b73832586ba4a09cc51f67bddcaf30c2f85fcca1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240294"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="292f6-103">Instalar os arquivos do servidor de mediação no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="292f6-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="292f6-104">**Resumo:** Saiba como instalar os arquivos do servidor de mediação no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="292f6-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="292f6-105">Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="292f6-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="292f6-106">Use as etapas neste tópico para executar o assistente de implantação do Skype for Business Server para instalar os arquivos do servidor de mediação em um computador que você adicionou a um pool do servidor de mediação depois de ter usado o construtor de topologias para definir e publicar o pool.</span><span class="sxs-lookup"><span data-stu-id="292f6-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="292f6-107">Ao instalar o servidor de mediação de arquivos, você também instala e atribui o certificado necessário para cada computador em um pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="292f6-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="292f6-108">Este tópico pressupõe que você já definiu e publicou um pool autônomo do servidor de mediação em sua topologia, conforme descrito em [implantar um servidor de mediação no construtor de topologias no Skype for Business Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="292f6-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="292f6-109">Para instalar os arquivos em um pool do Servidor de Mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="292f6-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="292f6-110">Na mídia de instalação, clique com o botão direito do mouse em _ \<instalação do Media\> _ **\Setup\amd64\Setup.exe**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="292f6-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="292f6-111">Na página **Local de instalação**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="292f6-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="292f6-p102">Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)</span><span class="sxs-lookup"><span data-stu-id="292f6-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="292f6-114">Na página do **Assistente de implantação do Skype for Business Server** , clique em **instalar ou atualizar o sistema do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="292f6-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="292f6-115">Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="292f6-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="292f6-116">Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="292f6-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="292f6-117">Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="292f6-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="292f6-118">Ao lado da **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **executar**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="292f6-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="292f6-119">Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="292f6-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="292f6-p103">Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribuí-lo.</span><span class="sxs-lookup"><span data-stu-id="292f6-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="292f6-123">Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="292f6-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="292f6-124">Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="292f6-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="292f6-125">No computador em que você está executando o painel de controle do Skype for Business Server, verifique na página **Topology** do painel de controle do Skype for Business Server que o status do serviço do servidor de mediação é mostrado como uma marca de seleção verde.</span><span class="sxs-lookup"><span data-stu-id="292f6-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="292f6-126">Se um X vermelho é exibido, selecione o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="292f6-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="292f6-127">No menu **Ações**, clique em **Iniciar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="292f6-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="292f6-128">Se você adicionou mais de um computador ao pool do servidor de mediação, execute as etapas neste procedimento em todos os outros computadores no pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="292f6-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="292f6-129">Se você não precisar instalar arquivos para o servidor de mediação para qualquer outro computador, siga os procedimentos em [Configurar troncos no Skype for Business Server](configure-trunks.md) para definir configurações para a conexão de tronco entre este pool de servidores de mediação (ou toda a mediação Servidores em um site) e seu par.</span><span class="sxs-lookup"><span data-stu-id="292f6-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

