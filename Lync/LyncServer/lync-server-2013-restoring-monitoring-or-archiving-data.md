---
title: 'Lync Server 2013: restaurando dados de monitoramento ou arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e44bf1fe66aa7c03caea2ba367f425f1094a9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="ca658-102">Restauração de dados de monitoramento ou arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca658-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca658-103">_**Última modificação do tópico:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ca658-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ca658-104">A restauração de dados de monitoramento e arquivamento não é necessária para que o Lync Server fique ativo e em execução após uma falha.</span><span class="sxs-lookup"><span data-stu-id="ca658-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="ca658-105">No entanto, se os dados de monitoramento e arquivamento forem críticos para sua organização, você desejará restaurar os dados após recriar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="ca658-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="ca658-106">O procedimento a seguir descreve como usar o SQL Server Management Studio para restaurar os dados de arquivamento ou monitoramento.</span><span class="sxs-lookup"><span data-stu-id="ca658-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="ca658-107">Para restaurar os dados de monitoramento ou arquivamento de um arquivo de backup</span><span class="sxs-lookup"><span data-stu-id="ca658-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="ca658-108">Faça logon no servidor que você está restaurando como um membro do grupo Administradores no computador local ou em um grupo com direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ca658-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="ca658-109">Abra o SQL Server Management Studio: clique em **Iniciar**, em **todos os programas**, em **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**e, em seguida, clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="ca658-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="ca658-110">Em **Conectar ao Servidor**, conecte-se à instância de SQL Server fornecendo pelo menos o nome do servidor e as informações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="ca658-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="ca658-111">Em **Pesquisador de Objetos**, clique com o botão direito do mouse em **Bancos de dados** e clique em **Restaurar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="ca658-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="ca658-112">Em **Selecionar uma página**, clique em **Geral** e selecione o nome do banco de dados em **Para o banco de dados** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ca658-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="ca658-113">Para um banco de dados de arquivamento, selecione **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="ca658-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="ca658-114">Para um banco de dados CDR (gravação de detalhes de chamada), selecione **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="ca658-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="ca658-115">Para um banco de dados QoE (Qualidade da Experiência), selecione **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="ca658-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="ca658-116">Clique em **Do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ca658-116">Click **From device**.</span></span>

7.  <span data-ttu-id="ca658-117">Em **Selecione os conjuntos de backup a serem restaurados**, clique no arquivo de backup e clique em **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="ca658-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="ca658-118">Em **Selecionar uma página**, clique em **Opções**, verifique se o caminho do arquivo de dados e o caminho de log estão na pasta correta e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca658-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="ca658-119">Para garantir que as listas de controle de acesso (ACLs) estejam corretas</span><span class="sxs-lookup"><span data-stu-id="ca658-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="ca658-120">Expanda **Bancos de dados**, expanda o banco de dados de arquivamento ou monitoramento, expanda **Segurança** e expanda **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ca658-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="ca658-121">Verifique se o grupo de domínio RTCComponentUniversalServices existe como um usuário.</span><span class="sxs-lookup"><span data-stu-id="ca658-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="ca658-122">Se o RTCComponentUniversalServices não existir nos **usuários**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ca658-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="ca658-123">Clique com o botão direito do mouse em **Usuários** e clique em **Novo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="ca658-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="ca658-124">Em **nome de logon**, digite o nome do grupo ausente, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="ca658-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="ca658-125">Em **Associação à função de banco de dados**, selecione a permissão **ServerRole** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca658-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca658-126">Não é necessário reiniciar o serviço de arquivamento ou monitoramento.</span><span class="sxs-lookup"><span data-stu-id="ca658-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

