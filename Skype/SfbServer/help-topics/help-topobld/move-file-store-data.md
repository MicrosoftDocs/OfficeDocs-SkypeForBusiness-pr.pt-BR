---
title: Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se você precisar remover o servidor de arquivos que está atuando atualmente como o armazenamento de arquivos para sua implantação do Skype for Business Server 2015, ou se precisar fazer outras alterações que tornariam o armazenamento de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento. Em seguida, você precisa executar as seguintes etapas:'
ms.openlocfilehash: 007bcb1ef383f9c18f7c4032f0ff17321b630201
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803141"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="243c1-104">Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="243c1-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="243c1-105">Se você precisar remover o servidor de arquivos que está atuando atualmente como o armazenamento de arquivos para sua implantação do Skype for Business Server 2015, ou se precisar fazer outras alterações que tornariam o armazenamento de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="243c1-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="243c1-106">Em seguida, você precisa executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="243c1-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="243c1-107">Desligue os serviços do Skype for Business Server 2015 que usam o armazenamento de arquivos que você planeja remover.</span><span class="sxs-lookup"><span data-stu-id="243c1-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="243c1-108">Defina o armazenamento de arquivos no Construtor de Topologias e publique as alterações para disponibilizar o novo armazenamento de arquivos para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="243c1-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="243c1-109">Mova os dados para o novo armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="243c1-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="243c1-110">Reinicie os servidores ou serviços.</span><span class="sxs-lookup"><span data-stu-id="243c1-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="243c1-111">Opcionalmente, remova o compartilhamento de arquivos e a pasta de arquivos antigos.</span><span class="sxs-lookup"><span data-stu-id="243c1-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="243c1-112">Para mover os dados do repositório de arquivos de um repositório para o novo</span><span class="sxs-lookup"><span data-stu-id="243c1-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="243c1-113">Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator no qual o Skype for Business Server 2015, Ferramentas Administrativas estão instalados.</span><span class="sxs-lookup"><span data-stu-id="243c1-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="243c1-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="243c1-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="243c1-115">Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="243c1-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="243c1-116">Para cada pool de Diretores, Diretor, servidor Standard Edition e pool de Front-End que usa o armazenamento de arquivos que você planeja remover, selecione o servidor ou pool, clique em Ação e clique em Parar todos os **serviços.**</span><span class="sxs-lookup"><span data-stu-id="243c1-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="243c1-117">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="243c1-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="243c1-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="243c1-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="243c1-119">Selecione um servidor ou pool que usa o armazenamento de arquivos e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="243c1-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="243c1-120">Clique com o botão direito do mouse no servidor ou pool e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="243c1-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="243c1-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span><span class="sxs-lookup"><span data-stu-id="243c1-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="243c1-122">Em **Definir Novo Armazenamento de Arquivos,** em **FQDN** do servidor de arquivos, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="243c1-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="243c1-123">Em **Compartilhamento de** arquivos, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="243c1-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="243c1-124">Esta etapa define um novo armazenamento de arquivos para uso no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="243c1-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="243c1-125">Você o define apenas uma vez, não para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="243c1-125">You define it only once, not for each server.</span></span> <span data-ttu-id="243c1-126">Antes de publicar a topologia, você deve criar o compartilhamento de arquivos definido no servidor de arquivos especificado.</span><span class="sxs-lookup"><span data-stu-id="243c1-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="243c1-127">Para detalhes, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="243c1-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="243c1-128">Para cada servidor ou pool que usa o armazenamento de arquivos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="243c1-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="243c1-129">Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades.**</span><span class="sxs-lookup"><span data-stu-id="243c1-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="243c1-130">Em **Editar Propriedades**, em **Associações**, no **Armazenamento** de arquivos , selecione o novo compartilhamento de arquivo e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="243c1-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="243c1-131">Publique a topologia, verifique o status de replicação e execute o Assistente de Implantação do Skype for Business Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="243c1-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="243c1-132">Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="243c1-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="243c1-133">Inicie um prompt de comando: clique em **Iniciar,** **clique** em Executar e digite cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="243c1-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="243c1-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="243c1-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="243c1-135">A opção /S copia arquivos, diretórios e subdireários.</span><span class="sxs-lookup"><span data-stu-id="243c1-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="243c1-136">A opção /XF ignora todos os arquivos chamados Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="243c1-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="243c1-137">Versões atuais do robocopy.exe com a opção /MT aumentam muito a velocidade da cópia usando vários threads.</span><span class="sxs-lookup"><span data-stu-id="243c1-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="243c1-138">Para a opção /LOG, use um caminho de diretório e um nome de arquivo de log na forma de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="243c1-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="243c1-139">Essa opção cria um arquivo de log de operações no local nomeado.</span><span class="sxs-lookup"><span data-stu-id="243c1-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="243c1-140">Quando a cópia de dados estiver concluída, no Painel de Controle do Lync Server, clique em **Topologia** e em **Status.**</span><span class="sxs-lookup"><span data-stu-id="243c1-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="243c1-141">Para cada servidor ou pool onde você interrompeu serviços, selecione o servidor ou pool, clique em Ação **e** clique em Iniciar todos **os serviços.**</span><span class="sxs-lookup"><span data-stu-id="243c1-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="243c1-142">Remova o repositório de arquivos antigo da topologia e publique-a.</span><span class="sxs-lookup"><span data-stu-id="243c1-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="243c1-143">Para detalhes, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="243c1-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="243c1-144">(Opcional) Faça logon no computador que contém o repositório de arquivos que foi removido como membro do grupo Administradores local ou grupo Admins. de Domínio e remova o compartilhamento de arquivos e o diretório antigos.</span><span class="sxs-lookup"><span data-stu-id="243c1-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="243c1-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="243c1-145">See also</span></span>

[<span data-ttu-id="243c1-146">Reatribuir um servidor para um repositório de arquivo diferente</span><span class="sxs-lookup"><span data-stu-id="243c1-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="243c1-147">Remover um armazenamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="243c1-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
