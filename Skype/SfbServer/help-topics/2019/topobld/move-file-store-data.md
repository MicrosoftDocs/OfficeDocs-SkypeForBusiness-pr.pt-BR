---
title: Dados do repositório de arquivos de movimentação para um novo repositório de arquivos no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Se você precisa remover o servidor de arquivos que esteja atuando como o repositório de arquivos para seu Skype para implantação de servidor de negócios ou se você precisar fazer outras alterações que tornaria o arquivo atual armazenam indisponível, você precisará criar um novo compartilhamento. Em seguida deverá executar as seguintes etapas:'
ms.openlocfilehash: d11840e182bc9af0da02c440dd91fc224e7396cc
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069241"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="7b086-104">Dados do repositório de arquivos de movimentação para um novo repositório de arquivos no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7b086-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>
 
<span data-ttu-id="7b086-105">Se você precisa remover o servidor de arquivos que esteja atuando como o repositório de arquivos para seu Skype para implantação de servidor de negócios ou se você precisar fazer outras alterações que tornaria o arquivo atual armazenam indisponível, você precisará criar um novo compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="7b086-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="7b086-106">Em seguida deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7b086-106">Then you need to perform the following steps:</span></span>
  
1. <span data-ttu-id="7b086-107">Desligue o Skype para serviços de Business Server que usam o repositório de arquivos que você planeja remover.</span><span class="sxs-lookup"><span data-stu-id="7b086-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>
    
2. <span data-ttu-id="7b086-108">Definir o repositório de arquivos no construtor de topologia e publicar as alterações para disponibilizar o novo arquivo de repositório para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="7b086-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>
    
3. <span data-ttu-id="7b086-109">Mova os dados para o novo repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7b086-109">Move the data to the new file store.</span></span>
    
4. <span data-ttu-id="7b086-110">Reinicie os servidores ou os serviços.</span><span class="sxs-lookup"><span data-stu-id="7b086-110">Restart the servers or services.</span></span>
    
5. <span data-ttu-id="7b086-111">Opcionalmente, remova o compartilhamento de arquivos ou a pasta de arquivos antiga.</span><span class="sxs-lookup"><span data-stu-id="7b086-111">Optionally, remove the old file share and file folder.</span></span>
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="7b086-112">Para mover os dados do repositório de arquivos de um repositório para outro</span><span class="sxs-lookup"><span data-stu-id="7b086-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="7b086-113">Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator onde o Skype para Business Server, ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="7b086-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>
    
2.  <span data-ttu-id="7b086-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="7b086-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7b086-115">Na barra de navegação esquerda, clique em **Topologia** e em **Status**. </span><span class="sxs-lookup"><span data-stu-id="7b086-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span> 
    
4. <span data-ttu-id="7b086-116">Para cada pool de diretores, diretor, servidor Standard Edition e pool de Front-End que usa o repositório de arquivos que você planeja remover, selecione o servidor ou pool, clique em **ação**e, em seguida, clique em **Parar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="7b086-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span> 
    
5. <span data-ttu-id="7b086-117">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7b086-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
6. <span data-ttu-id="7b086-118">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique **Skype para o construtor de topologia de servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="7b086-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
7. <span data-ttu-id="7b086-119">Selecione um servidor ou pool que usa o repositório de arquivos e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b086-119">Select a server or pool that uses the file store, and do the following:</span></span>
    
1. <span data-ttu-id="7b086-120">Clique com o botão direito do mouse no servidor ou no pool e em **Editar Propriedades**. </span><span class="sxs-lookup"><span data-stu-id="7b086-120">Right-click the server or pool, and then click **Edit Properties**.</span></span> 
    
2. <span data-ttu-id="7b086-121">Em **Editar propriedades**, **Associações**, **Repositório de arquivos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7b086-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>
    
3. <span data-ttu-id="7b086-p103">Em **Definir Novo Repositório de Arquivos**, em **FQDN do servidor de arquivo**, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos. Em **Compartilhamento de arquivos**, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b086-p103">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server. Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b086-124">Essa etapa define um novo repositório de arquivos para uso no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="7b086-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="7b086-125">Você o define apenas uma vez, não para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="7b086-125">You define it only once, not for each server.</span></span> <span data-ttu-id="7b086-126">Antes de você publicar a topologia, deverá criar o compartilhamento de arquivos definido no servidor de arquivos definido.</span><span class="sxs-lookup"><span data-stu-id="7b086-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="7b086-127">Para obter detalhes, consulte [Define the File Store para o Front-End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b086-127">For details, see [Define the File Store for the Front End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span> 
  
8. <span data-ttu-id="7b086-128">Para cada servidor ou pool que usa o repositório de arquivos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b086-128">For each server or pool that uses the file store, do the following:</span></span>
    
1. <span data-ttu-id="7b086-129">Clique com o botão direito do mouse no servidor ou no pool e em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7b086-129">Right-click the server or pool, and then click **Edit properties**.</span></span>
    
2. <span data-ttu-id="7b086-130">Em **Editar Propriedades**, **Associações**, **Repositório de arquivos**, selecione o novo compartilhamento de arquivos e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b086-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>
    
9. <span data-ttu-id="7b086-131">Publique a topologia, verifique o status de replicação e execute o Skype para o Assistente de implantação de servidor de negócios conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7b086-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="7b086-132">Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b086-132">For details, see [Common Procedures for Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>
    
10. <span data-ttu-id="7b086-133">Inicie um prompt de comando: clique em **Iniciar**, clique em **Executar**e digite cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="7b086-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>
    
11. <span data-ttu-id="7b086-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b086-134">At the command line, type the following:</span></span>
    
  ```
  Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
  ```

    > [!TIP]
    > <span data-ttu-id="7b086-135">A opção /S copia sobre os arquivos, diretórios e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="7b086-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="7b086-136">A opção /XF ignora os arquivos nomeados como Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="7b086-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="7b086-137">As versões atuais de robocopy.exe com a opção /MT aumentam significativamente a velocidade da cópia usando vários threads.</span><span class="sxs-lookup"><span data-stu-id="7b086-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="7b086-138">Para o switch /LOG, use um diretório caminho e o log de nome de arquivo no formato de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="7b086-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="7b086-139">Essa opção cria um arquivo de log das operações no local nomeado.</span><span class="sxs-lookup"><span data-stu-id="7b086-139">This switch creates a log file of operations at the named location.</span></span> 
  
12. <span data-ttu-id="7b086-140">Quando a cópia de dados estiver concluída, no painel de controle do Lync Server, clique em **topologia**e, em seguida, clique em **Status**.</span><span class="sxs-lookup"><span data-stu-id="7b086-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>
    
13. <span data-ttu-id="7b086-141">Para cada servidor ou pool cujos serviços você interrompeu, selecione o servidor ou pool, clique em **Ação** e em **Iniciar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="7b086-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span> 
    
14. <span data-ttu-id="7b086-142">Remova o antigo repositório de arquivos da topologia e publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="7b086-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="7b086-143">Para obter detalhes, consulte [Remover um repositório de arquivos](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b086-143">For details, see [Remove a file store](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>
    
15. <span data-ttu-id="7b086-144">(Opcional) Faça logon no computador que contém o repositório de arquivos que você acabou de remover como membro do grupo local de administradores ou do grupo de administradores de domínio e remova o antigo diretório e compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7b086-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b086-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7b086-145">See also</span></span>

[<span data-ttu-id="7b086-146">Reatribuir um servidor para um repositório de arquivo diferente</span><span class="sxs-lookup"><span data-stu-id="7b086-146">Reassign a Server to a Different File Store</span></span>](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[<span data-ttu-id="7b086-147">Remover um repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="7b086-147">Remove a file store</span></span>](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)