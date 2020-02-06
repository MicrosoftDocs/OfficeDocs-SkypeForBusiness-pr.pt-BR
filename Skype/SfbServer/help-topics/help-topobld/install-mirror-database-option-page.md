---
title: Instalar Página de Opção de Banco de Dados de Espelhamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Defina as configurações do banco de dados espelho definindo o seguinte:'
ms.openlocfilehash: dde906a5b4d9544cb357e2eed20cb7769f232be8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819793"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="2d8e2-103">Instalar Página de Opção de Banco de Dados de Espelhamento</span><span class="sxs-lookup"><span data-stu-id="2d8e2-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="2d8e2-104">Defina as **configurações do banco de dados espelho** definindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d8e2-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="2d8e2-105">Digite o **caminho para compartilhamento de arquivos** para definir o local dos arquivos do SQL Server de backup do banco de dados que está sendo espelhado.</span><span class="sxs-lookup"><span data-stu-id="2d8e2-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d8e2-106">A instância primária do SQL Server (instância nomeada ou padrão) deve ter permissões de gravação para o compartilhamento de arquivos que você definir aqui.</span><span class="sxs-lookup"><span data-stu-id="2d8e2-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="2d8e2-107">A instância de espelhamento do SQL Server (instância nomeada ou padrão) deve ter permissões de leitura para o mesmo compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2d8e2-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="2d8e2-108">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d8e2-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2d8e2-109">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d8e2-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2d8e2-110">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="2d8e2-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d8e2-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="2d8e2-111">See also</span></span>

[<span data-ttu-id="2d8e2-112">Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d8e2-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
