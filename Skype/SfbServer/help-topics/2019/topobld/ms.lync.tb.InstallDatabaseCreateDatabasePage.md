---
title: Instalar e Criar Bancos de Dados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Selecione os bancos de dados que você deseja criar para sua implantação. Por padrão, o banco de dados será criado no SQL Server definido no site definido e implantará e configurará automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.
ms.openlocfilehash: 160b42e510fc54b3f03375a0c86bc9f6bdf83f5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100047"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="e6e70-104">Instalar e Criar Bancos de Dados</span><span class="sxs-lookup"><span data-stu-id="e6e70-104">Install and Create Databases</span></span>

<span data-ttu-id="e6e70-105">Selecione os bancos de dados que você deseja criar para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e6e70-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="e6e70-106">Por padrão, o banco de dados será criado no SQL Server definido no site definido e implantará e configurará automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="e6e70-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="e6e70-p103">**Selecione os bancos de dados que deseja criar**: marque a caixa de seleção de qualquer banco de dados que você pretenda implantar e configurar. Marque a caixa de seleção ou qualquer um ou todos os bancos de dados que você implantará.</span><span class="sxs-lookup"><span data-stu-id="e6e70-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="e6e70-109">O SQL Server já deve ter sido configurado para a instância (se alguma) e as portas de firewall devem ser abertas para acomodar a instância para a que você está implantando os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="e6e70-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="e6e70-110">Para obter detalhes, consulte [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span><span class="sxs-lookup"><span data-stu-id="e6e70-110">For details, see [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span></span>

 <span data-ttu-id="e6e70-111">**Avançado**: clique na SQL Server e clique no botão **Avançado** para escolher opções para os locais de arquivo de banco de dados em sua SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6e70-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="e6e70-112">Para obter detalhes sobre o posicionamento avançado de arquivo de banco de dados, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span><span class="sxs-lookup"><span data-stu-id="e6e70-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span></span>

 <span data-ttu-id="e6e70-113">**Voltar**: clicar nesse botão faz com que você volte para a tela anterior (talvez não esteja sempre disponível, com base na forma que você chegou até essa caixa de diálogo).</span><span class="sxs-lookup"><span data-stu-id="e6e70-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="e6e70-114">**Avançar**: clicar nesse botão confirma sua seleção na caixa de diálogo atual e o leva até a próxima caixa de diálogo para configurar informações adicionais</span><span class="sxs-lookup"><span data-stu-id="e6e70-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="e6e70-115">**Cancelar**: clicar nesse botão encerrará a configuração e descartará suas alterações.</span><span class="sxs-lookup"><span data-stu-id="e6e70-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="e6e70-116">Algumas telas de configuração, mas não todas, perguntarão se você deseja encerrar e descartar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="e6e70-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="e6e70-117">Selecionar **Sim** fechará a configuração atual e fechará a configuração atual e o retornará ao Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="e6e70-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="e6e70-118">Selecionar **Não** o levará de volta até a caixa de diálogo de configuração atual e permitirá que você continue a configuração.</span><span class="sxs-lookup"><span data-stu-id="e6e70-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="e6e70-119">**Ajudar**: clicar no botão **Ajuda** exibe essas informações de ajuda associadas à caixa de diálogo de configuração atual.</span><span class="sxs-lookup"><span data-stu-id="e6e70-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>