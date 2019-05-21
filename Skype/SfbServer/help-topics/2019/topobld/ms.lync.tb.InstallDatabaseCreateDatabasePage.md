---
title: Instalar e Criar Bancos de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Selecione os bancos de dados que você deseja criar para a implantação. Por padrão, o banco de dados será criado no SQL Server definido no site definido e irá implantar e configurar automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.
ms.openlocfilehash: f4ee4bb5c5b6dcfe66680fdc163930470f1b50a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291676"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="ef918-104">Instalar e Criar Bancos de Dados</span><span class="sxs-lookup"><span data-stu-id="ef918-104">Install and Create Databases</span></span>

<span data-ttu-id="ef918-105">Selecione os bancos de dados que você deseja criar para a implantação.</span><span class="sxs-lookup"><span data-stu-id="ef918-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="ef918-106">Por padrão, o banco de dados será criado no SQL Server definido no site definido e irá implantar e configurar automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="ef918-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="ef918-107">**Selecione os bancos de dados que você deseja criar**: marque a caixa de seleção de todos os bancos de dados que você pretende implantar e configurar.</span><span class="sxs-lookup"><span data-stu-id="ef918-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="ef918-108">Marque a caixa de seleção de qualquer ou de todos os bancos de dados que você implantar.</span><span class="sxs-lookup"><span data-stu-id="ef918-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="ef918-109">O SQL Server já deve ter sido configurado para a instância (se houver) e as portas de firewall devem ser abertas para acomodar a instância para a qual você está implantando os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="ef918-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="ef918-110">Para obter detalhes, consulte [Configurar o SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef918-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="ef918-111">**Avançado**: clique no SQL Server e clique no botão **avançado** para escolher as opções dos locais do arquivo de banco de dados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ef918-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="ef918-112">Para obter detalhes sobre o posicionamento avançado de arquivos do banco de dados, consulte [instalação do banco de dados usando o Shell de gerenciamento](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef918-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="ef918-113">**Voltar**: clicar neste botão retorna para a tela anterior (nem sempre pode estar disponível, com base em como você chegou nesta caixa de diálogo).</span><span class="sxs-lookup"><span data-stu-id="ef918-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="ef918-114">Em **seguida**: clicar neste botão confirma sua seleção na caixa de diálogo atual e leva você para a próxima caixa de diálogo para configurar informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ef918-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="ef918-115">**Cancelar**: clicar neste botão encerrará a configuração e descartará suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ef918-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="ef918-116">Algumas telas de configuração, mas nem todas irão perguntar se você deseja encerrar e descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="ef918-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="ef918-117">Selecionar **Sim** fechará a configuração atual e fechará a configuração atual e retornará você ao construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="ef918-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="ef918-118">Selecionar **não** vai retornar você à caixa de diálogo configuração atual e permitir que você continue a configuração.</span><span class="sxs-lookup"><span data-stu-id="ef918-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="ef918-119">**Ajuda**: clicar no botão **ajuda** exibe estas informações de ajuda associadas à caixa de diálogo configuração atual.</span><span class="sxs-lookup"><span data-stu-id="ef918-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


