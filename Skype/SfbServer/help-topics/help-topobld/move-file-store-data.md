---
title: Mover dados do repositório de arquivos para um novo repositório de arquivos no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se você precisar remover o servidor de arquivos que está atuando atualmente como o repositório de arquivos para sua implantação do Skype for Business Server 2015, ou se precisar fazer outras alterações que tornaram o repositório de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento. Em seguida, você precisará executar as seguintes etapas:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215582"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="d90e1-104">Mover dados do repositório de arquivos para um novo repositório de arquivos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d90e1-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="d90e1-105">Se você precisar remover o servidor de arquivos que está atuando atualmente como o repositório de arquivos para sua implantação do Skype for Business Server 2015, ou se precisar fazer outras alterações que tornaram o repositório de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="d90e1-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="d90e1-106">Em seguida, você precisará executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d90e1-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="d90e1-107">Encerre os serviços do Skype for Business Server 2015 que usam o repositório de arquivos que você planeja remover.</span><span class="sxs-lookup"><span data-stu-id="d90e1-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="d90e1-108">Defina o repositório de arquivos no construtor de topologia e publique as alterações para disponibilizar o novo repositório de arquivos para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d90e1-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="d90e1-109">Mova os dados para o novo repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d90e1-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="d90e1-110">Reinicie os servidores ou serviços.</span><span class="sxs-lookup"><span data-stu-id="d90e1-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="d90e1-111">Opcionalmente, remova o compartilhamento de arquivo e a pasta de arquivo antigos.</span><span class="sxs-lookup"><span data-stu-id="d90e1-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="d90e1-112">Para mover os dados do repositório de arquivos de um repositório para o novo</span><span class="sxs-lookup"><span data-stu-id="d90e1-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="d90e1-113">Faça logon em um computador como membro do grupo grupo rtcuniversersalserveradmins ou CsServerAdministrator onde o Skype for Business Server 2015, as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="d90e1-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="d90e1-114">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d90e1-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d90e1-115">Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="d90e1-116">Para cada pool de diretores, diretor, servidor Standard Edition e pool de front-ends que usa o repositório de arquivos que você planeja remover, selecione o servidor ou pool, clique em **ação**e em **parar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="d90e1-117">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d90e1-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="d90e1-118">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="d90e1-119">Selecione um servidor ou pool que usa o repositório de arquivos e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d90e1-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="d90e1-120">Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="d90e1-121">Em **Editar propriedades**, em **associações**, em **repositório de arquivos**, clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="d90e1-122">Em **definir novo repositório de arquivos**, em **FQDN do servidor de arquivos**, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d90e1-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="d90e1-123">Em **compartilhamento de arquivos**, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="d90e1-124">Esta etapa define um novo repositório de arquivos para uso no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="d90e1-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="d90e1-125">Você pode defini-la somente uma vez, e não para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="d90e1-125">You define it only once, not for each server.</span></span> <span data-ttu-id="d90e1-126">Antes de publicar a topologia, você deve criar o compartilhamento de arquivos definido no servidor de arquivos especificado.</span><span class="sxs-lookup"><span data-stu-id="d90e1-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="d90e1-127">Para detalhes, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="d90e1-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="d90e1-128">Para cada servidor ou pool que usa o repositório de arquivos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d90e1-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="d90e1-129">Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="d90e1-130">Em **Editar propriedades**, em **associações**, em **repositório de arquivos**, selecione o novo compartilhamento de arquivos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="d90e1-131">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Skype for Business Server, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d90e1-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="d90e1-132">Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="d90e1-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="d90e1-133">Inicie um prompt de comando: clique em **Iniciar**, clique em **executar**e digite cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="d90e1-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="d90e1-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d90e1-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="d90e1-135">A opção/S copia sobre arquivos, diretórios e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="d90e1-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="d90e1-136">A opção/XF ignora qualquer arquivo chamado Meeting. Active.</span><span class="sxs-lookup"><span data-stu-id="d90e1-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="d90e1-137">Versões atuais do robocopy.exe com a opção /MT aumentam muito a velocidade da cópia usando vários threads.</span><span class="sxs-lookup"><span data-stu-id="d90e1-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="d90e1-138">Para a opção/LOG, use um caminho de diretório e um nome de arquivo de log na forma de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="d90e1-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="d90e1-139">Essa opção cria um arquivo de log de operações no local nomeado.</span><span class="sxs-lookup"><span data-stu-id="d90e1-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="d90e1-140">Quando a cópia de dados estiver concluída, no painel de controle do Lync Server, clique em **topologia**e em **status**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="d90e1-141">Para cada servidor ou pool em que você interrompeu serviços, selecione o servidor ou pool, clique em **ação**e em **Iniciar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="d90e1-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="d90e1-142">Remova o repositório de arquivos antigo da topologia e publique-a.</span><span class="sxs-lookup"><span data-stu-id="d90e1-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="d90e1-143">Para detalhes, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="d90e1-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="d90e1-144">(Opcional) Faça logon no computador que contém o repositório de arquivos que foi removido como membro do grupo Administradores local ou grupo Admins. de Domínio e remova o compartilhamento de arquivos e o diretório antigos.</span><span class="sxs-lookup"><span data-stu-id="d90e1-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d90e1-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="d90e1-145">See also</span></span>

[<span data-ttu-id="d90e1-146">Reatribuir um servidor para um repositório de arquivo diferente</span><span class="sxs-lookup"><span data-stu-id="d90e1-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="d90e1-147">Remover um repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="d90e1-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
