---
title: Instalar e Criar Bancos de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Você seleciona os bancos de dados que você deseja criar sua implantação. Por padrão, o banco de dados será criado no SQL Server definido no site do definido e será automaticamente implantar e configurar os arquivos de banco de dados com base em você estiver colocando os bancos de dados no SQL Server.
ms.openlocfilehash: 94c16a4bc0e51c10939949e02d07d8233744b40f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888601"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="d84ac-104">Instalar e Criar Bancos de Dados</span><span class="sxs-lookup"><span data-stu-id="d84ac-104">Install and Create Databases</span></span>

<span data-ttu-id="d84ac-105">Você seleciona os bancos de dados que você deseja criar sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d84ac-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="d84ac-106">Por padrão, o banco de dados será criado no SQL Server definido no site do definido e será automaticamente implantar e configurar os arquivos de banco de dados com base em você estiver colocando os bancos de dados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d84ac-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="d84ac-107">**Selecione os bancos de dados que você deseja criar**: marque a caixa de seleção de qualquer banco de dados que você pretende implantar e configurar.</span><span class="sxs-lookup"><span data-stu-id="d84ac-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="d84ac-108">Marque a caixa de seleção de um ou todos os bancos de dados que você implantará.</span><span class="sxs-lookup"><span data-stu-id="d84ac-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="d84ac-109">O SQL Server deve já foram configurado para a instância (se houver) e portas do firewall devem ser abertas para acomodar a instância que você estiver implantando os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d84ac-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="d84ac-110">Para obter detalhes, consulte [Configurar o SQL Server para o Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="d84ac-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="d84ac-111">**Avançado**: clique no SQL Server e clique no botão **Avançado** para escolher opções de banco de dados de locais de arquivos no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d84ac-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="d84ac-112">Para obter detalhes sobre a localização do arquivo de banco de dados avançado, consulte [Banco de dados de instalação usando o Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="d84ac-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="d84ac-113">**Voltar**: clicar nesse botão você retorna à tela anterior (talvez não ser sempre disponível, com base em como que você chegou até essa caixa de diálogo).</span><span class="sxs-lookup"><span data-stu-id="d84ac-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="d84ac-114">**Avançar**: clicar nesse botão confirma sua seleção na caixa de diálogo atual e vai para a próxima caixa de diálogo para configurar informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d84ac-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="d84ac-115">**Cancelar**: clicar nesse botão será encerre a configuração e descartar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="d84ac-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="d84ac-116">Alguns, mas nem todas as telas de configuração perguntará se você deseja encerrar e descartar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="d84ac-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="d84ac-117">Selecionar **Sim** fechará a configuração atual e fechar a configuração atual e voltar você para o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="d84ac-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="d84ac-118">Selecionar **não** , você retorna à caixa de diálogo configuração atual e permitem que você continuar a configuração.</span><span class="sxs-lookup"><span data-stu-id="d84ac-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="d84ac-119">**Ajudar**: clicando no botão **Ajuda** exibe essas informações da Ajuda associadas à caixa de diálogo configuração atual.</span><span class="sxs-lookup"><span data-stu-id="d84ac-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


