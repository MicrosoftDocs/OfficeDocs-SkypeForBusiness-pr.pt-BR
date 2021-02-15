---
title: Instalar os arquivos do Servidor de Mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumo: saiba como instalar os arquivos para o Servidor de Mediação no Skype for Business Server.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830791"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="40c11-103">Instalar os arquivos do Servidor de Mediação no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40c11-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="40c11-104">**Resumo:** Saiba como instalar os arquivos para o Servidor de Mediação no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40c11-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="40c11-105">Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="40c11-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="40c11-106">Use as etapas neste tópico para executar o Assistente de Implantação do Skype for Business Server para instalar os arquivos do Servidor de Mediação em um computador que você adicionou a um pool de Servidor de Mediação depois de usar o Construtor de Topologias para definir e publicar o pool.</span><span class="sxs-lookup"><span data-stu-id="40c11-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="40c11-107">Ao instalar arquivos do Servidor de Mediação, você também instala e atribui o certificado exigido por cada computador em um pool do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="40c11-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="40c11-108">Este tópico assume que você já definiu e publicou um pool de Servidor de Mediação autônomo em sua topologia, conforme descrito em Implantar um Servidor de Mediação no Construtor de Topologias no [Skype for Business Server.](deploy-a-mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="40c11-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="40c11-109">Para instalar os arquivos em um pool do Servidor de Mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="40c11-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="40c11-110">Na mídia de instalação, clique com o\Setup\amd64\Setup.exee clique _\<installation media\>_ \*\*\*\* em Executar **como Administrador.**</span><span class="sxs-lookup"><span data-stu-id="40c11-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="40c11-111">Na página **Local de instalação**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="40c11-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="40c11-p102">Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)</span><span class="sxs-lookup"><span data-stu-id="40c11-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="40c11-114">Na página **Assistente de Implantação do Skype for Business Server,** clique em **Instalar ou Atualizar o Sistema do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="40c11-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="40c11-115">Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="40c11-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="40c11-116">Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="40c11-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="40c11-117">Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="40c11-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="40c11-118">Próximo à **Etapa 2: Configurar ou Remover Componentes do Skype for Business Server,** clique em **Executar** e em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="40c11-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="40c11-119">Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="40c11-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="40c11-p103">Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribui-lo.</span><span class="sxs-lookup"><span data-stu-id="40c11-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="40c11-123">Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="40c11-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="40c11-124">Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="40c11-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="40c11-125">No computador em que você está executando o Painel de Controle do Skype for Business Server, verifique na página **Topologia** do Painel de Controle do Skype for Business Server se o status do serviço do Servidor de Mediação é mostrado como uma marca de seleção verde.</span><span class="sxs-lookup"><span data-stu-id="40c11-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="40c11-126">Se um X vermelho é exibido, selecione o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="40c11-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="40c11-127">No menu **Ações**, clique em **Iniciar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="40c11-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="40c11-128">Se você adicionou mais de um computador ao pool do Servidor de Mediação, execute as etapas deste procedimento em todos os outros computadores no pool do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="40c11-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="40c11-129">Se você não precisar instalar arquivos para o Servidor de Mediação para outros [computadores,](configure-trunks.md) siga os procedimentos em Configurar troncos no Skype for Business Server para definir as configurações para a conexão de tronco entre esse pool do Servidor de Mediação (ou todos os Servidores de Mediação em um site) e seu par.</span><span class="sxs-lookup"><span data-stu-id="40c11-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

