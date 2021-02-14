---
title: Instalar Página de Opção de Banco de Dados de Espelhamento
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
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Define as Configurações de Banco de Dados definindo o seguinte:'
ms.openlocfilehash: 63e3795cc52b9b8e3601b2260df253fdcd2d9c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806891"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="67437-103">Instalar Página de Opção de Banco de Dados de Espelhamento</span><span class="sxs-lookup"><span data-stu-id="67437-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="67437-104">Define as **Configurações de Banco de Dados** definindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="67437-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="67437-105">Digite o **caminho para o compartilhamento de** arquivos para definir o local dos arquivos de backup do SQL Server para o banco de dados que está sendo espelhado.</span><span class="sxs-lookup"><span data-stu-id="67437-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="67437-106">A instância principal do SQL Server (instância nomeada ou padrão) deve ter permissões de gravação no compartilhamento de arquivos definido aqui.</span><span class="sxs-lookup"><span data-stu-id="67437-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="67437-107">A instância do SQL Server espelho (instância nomeada ou instância padrão) deve ter permissões de leitura para o mesmo compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="67437-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="67437-108">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="67437-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="67437-109">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="67437-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="67437-110">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="67437-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="67437-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="67437-111">See also</span></span>

[<span data-ttu-id="67437-112">Implantar espelhamento SQL para alta disponibilidade do Servidor #A0 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67437-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
