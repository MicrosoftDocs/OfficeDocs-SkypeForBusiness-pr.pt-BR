---
title: Instalar Página de Opções de Banco de Dados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log em seu SQL Server. As opções disponíveis são:'
ms.openlocfilehash: 392db6eb9b882ff66a9f15e1f5c4f0918cb140a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116069"
---
# <a name="install-database-options-page"></a><span data-ttu-id="853db-104">Instalar Página de Opções de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="853db-104">Install Database Options Page</span></span>

<span data-ttu-id="853db-105">Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log em seu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="853db-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="853db-106">As opções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="853db-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="853db-107">Selecione a opção que melhor se ajuste aos seus requisitos e políticas referentes ao posicionamento de arquivos de log e dados em seus SQL Server computadores.</span><span class="sxs-lookup"><span data-stu-id="853db-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="853db-108">**Determinar automaticamente o** local do arquivo de banco de dados : A opção padrão usa um algoritmo que determina o espaço disponível no SQL Server e distribui o banco de dados e os arquivos de log para obter o desempenho ideal.</span><span class="sxs-lookup"><span data-stu-id="853db-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="853db-109">**Use SQL Server de instância:** selecione essa opção para colocar arquivos de banco de dados e arquivos de log com base nas configurações de instância em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="853db-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="853db-110">As opções são normalmente gerenciadas e configuradas por seu Administrador de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="853db-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="853db-111">Us **these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span><span class="sxs-lookup"><span data-stu-id="853db-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="853db-112">Os caminhos inseridos podem ser modificados com base nos algoritmos de otimização de desempenho na instalação.</span><span class="sxs-lookup"><span data-stu-id="853db-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="853db-113">Para obter detalhes, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span><span class="sxs-lookup"><span data-stu-id="853db-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="853db-114">**OK**: clique no botão OK para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="853db-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="853db-115">**Cancelar**: clique em Cancelar para descartar quaisquer alterações e retornar à tela Instalar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="853db-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="853db-116">**Ajuda**: clique no botão Ajuda para acessar esta página de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="853db-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="853db-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="853db-117">See also</span></span>

[<span data-ttu-id="853db-118">Localização de arquivos de log e dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="853db-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)