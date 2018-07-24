---
title: Instalar página de opção de banco de dados de espelho
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Você pode configurar definições de banco de dados de espelho definindo o seguinte:'
ms.openlocfilehash: aadb4ddc61603a827ff1e9f2bc1c2d332ad8d7db
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974589"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="fe5f1-103">Instalar página de opção de banco de dados de espelho</span><span class="sxs-lookup"><span data-stu-id="fe5f1-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="fe5f1-104">Você pode configurar **Definições de banco de dados de espelho** definindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe5f1-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="fe5f1-105">Digite o **caminho do arquivo compartilhar** para definir o local dos arquivos de backup do SQL Server para o banco de dados sendo espelhado.</span><span class="sxs-lookup"><span data-stu-id="fe5f1-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe5f1-106">Instância do SQL Server principal (instância nomeada ou instância padrão) deve ter permissões de gravação para o compartilhamento de arquivos definidas aqui.</span><span class="sxs-lookup"><span data-stu-id="fe5f1-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="fe5f1-107">O espelho (instância nomeada ou instância padrão) a instância do SQL Server deve ter permissões de leitura para o mesmo compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="fe5f1-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
 <span data-ttu-id="fe5f1-108">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fe5f1-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="fe5f1-109">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fe5f1-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="fe5f1-110">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="fe5f1-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe5f1-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fe5f1-111">See also</span></span>

[<span data-ttu-id="fe5f1-112">Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe5f1-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)