---
title: Adicionar Repositório de Arquivo de Servidor de Arquivamento
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou pode especificar um compartilhamento de arquivos novo, especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deve estar localizado e um nome de pasta para ele.
ms.openlocfilehash: 160289766fcdbf38f706962329e61d1d72e96af5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388819"
---
# <a name="add-archiving-server-file-store"></a>Adicionar Repositório de Arquivo do Servidor de Arquivamento

Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou pode especificar um compartilhamento de arquivos novo, especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deve estar localizado e um nome de pasta para ele.

> [!IMPORTANT]
> Você pode definir um compartilhamento de arquivos no Construtor de Topologia antes de criar o compartilhamento de arquivos, mas você deve criar um compartilhamento de arquivos no local definido antes de publicar a topologia. > Quando você adiciona um Servidor de Arquivamento à sua topologia, o Construtor de Topologias deve ser capaz de configurar o armazenamento de arquivos de arquivamento e configurar listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos. Isso exige que, quando executar o Construtor de Topologia para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos.

Para obter detalhes sobre o suporte [de](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) armazenamento para compartilhamentos de arquivos, consulte [File Armazenamento Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) na documentação de Suporte e SQL Server Posicionamento de Arquivos de Dados e Log na documentação de Implantação. Para obter detalhes sobre colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) na documentação de Suporte.