---
title: Mover dados do repositório de arquivos para um novo repositório de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Se você precisar remover o servidor de arquivos que está atuando como o repositório de arquivos para a implantação do Skype for Business Server, ou se precisar fazer outras alterações para tornar o repositório de arquivos atual indisponível, primeiro você precisará criar um novo compartilhamento. Em seguida deverá executar as seguintes etapas:'
ms.openlocfilehash: 00fa169eb000c9575609359c146a9db24c94de48
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794450"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="c74dd-104">Mover dados do repositório de arquivos para um novo repositório de arquivos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c74dd-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="c74dd-105">Se você precisar remover o servidor de arquivos que está atuando como o repositório de arquivos para a implantação do Skype for Business Server, ou se precisar fazer outras alterações para tornar o repositório de arquivos atual indisponível, primeiro você precisará criar um novo compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="c74dd-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="c74dd-106">Em seguida deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c74dd-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="c74dd-107">Desligue os serviços do Skype for Business Server que usam o repositório de arquivos que você planeja remover.</span><span class="sxs-lookup"><span data-stu-id="c74dd-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="c74dd-108">Defina o repositório de arquivos no construtor de topologias e publique as alterações para disponibilizar o novo repositório de arquivos para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c74dd-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="c74dd-109">Mova os dados para o novo repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c74dd-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="c74dd-110">Reinicie os servidores ou os serviços.</span><span class="sxs-lookup"><span data-stu-id="c74dd-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="c74dd-111">Opcionalmente, remova o compartilhamento de arquivos ou a pasta de arquivos antiga.</span><span class="sxs-lookup"><span data-stu-id="c74dd-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="c74dd-112">Para mover os dados do repositório de arquivos de um repositório para outro</span><span class="sxs-lookup"><span data-stu-id="c74dd-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="c74dd-113">Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator em que o Skype for Business Server, ferramentas administrativas, estejam instaladas.</span><span class="sxs-lookup"><span data-stu-id="c74dd-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="c74dd-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c74dd-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c74dd-115">Na barra de navegação esquerda, clique em **Topologia** e em **Status**. </span><span class="sxs-lookup"><span data-stu-id="c74dd-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="c74dd-116">Para cada pool de directors, diretor, servidor Standard Edition e pool de front-end que usa o repositório de arquivos que você planeja remover, selecione o servidor ou o pool, clique em **ação**e clique em **parar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="c74dd-117">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c74dd-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="c74dd-118">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server**e em **Construtor de topologias do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="c74dd-119">Selecione um servidor ou pool que usa o repositório de arquivos e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c74dd-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="c74dd-120">Clique com o botão direito do mouse no servidor ou no pool e em **Editar Propriedades**. </span><span class="sxs-lookup"><span data-stu-id="c74dd-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="c74dd-121">Em **Editar propriedades**, **Associações**, **Repositório de arquivos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="c74dd-p103">Em **Definir Novo Repositório de Arquivos**, em **FQDN do servidor de arquivo**, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos. Em **Compartilhamento de arquivos**, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-p103">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server. Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="c74dd-124">Esta etapa define um novo repositório de arquivos para uso no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c74dd-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="c74dd-125">Você o define apenas uma vez, não para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="c74dd-125">You define it only once, not for each server.</span></span> <span data-ttu-id="c74dd-126">Antes de você publicar a topologia, deverá criar o compartilhamento de arquivos definido no servidor de arquivos definido.</span><span class="sxs-lookup"><span data-stu-id="c74dd-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="c74dd-127">Para obter detalhes, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="c74dd-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="c74dd-128">Para cada servidor ou pool que usa o repositório de arquivos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c74dd-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="c74dd-129">Clique com o botão direito do mouse no servidor ou no pool e em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="c74dd-130">Em **Editar Propriedades**, **Associações**, **Repositório de arquivos**, selecione o novo compartilhamento de arquivos e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="c74dd-131">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Skype for Business Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c74dd-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="c74dd-132">Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="c74dd-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="c74dd-133">Inicie um prompt de comando: clique em **Iniciar**, clique em **executar**e digite cmd. exe.</span><span class="sxs-lookup"><span data-stu-id="c74dd-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="c74dd-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c74dd-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="c74dd-135">A opção /S copia sobre os arquivos, diretórios e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c74dd-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="c74dd-136">A opção /XF ignora os arquivos nomeados como Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="c74dd-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="c74dd-137">As versões atuais de robocopy.exe com a opção /MT aumentam significativamente a velocidade da cópia usando vários threads.</span><span class="sxs-lookup"><span data-stu-id="c74dd-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="c74dd-138">Para a opção/LOG, use um caminho de diretório e um nome de arquivo de log na forma de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="c74dd-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="c74dd-139">Essa opção cria um arquivo de log das operações no local nomeado.</span><span class="sxs-lookup"><span data-stu-id="c74dd-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="c74dd-140">Quando a cópia de dados estiver concluída, no painel de controle do Lync Server, clique em **topologia**e, em seguida, clique em **status**.</span><span class="sxs-lookup"><span data-stu-id="c74dd-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="c74dd-141">Para cada servidor ou pool cujos serviços você interrompeu, selecione o servidor ou pool, clique em **Ação** e em **Iniciar todos os serviços**.         </span><span class="sxs-lookup"><span data-stu-id="c74dd-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="c74dd-p107">Remova o antigo repositório de arquivos da topologia e publique a topologia. Para obter detalhes, veja [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="c74dd-p107">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="c74dd-144">(Opcional) Faça logon no computador que contém o repositório de arquivos que você acabou de remover como membro do grupo local de administradores ou do grupo de administradores de domínio e remova o antigo diretório e compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c74dd-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="c74dd-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="c74dd-145">See also</span></span>

[<span data-ttu-id="c74dd-146">Reatribuir um servidor a um repositório de arquivos diferente</span><span class="sxs-lookup"><span data-stu-id="c74dd-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="c74dd-147">Remover um repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="c74dd-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
