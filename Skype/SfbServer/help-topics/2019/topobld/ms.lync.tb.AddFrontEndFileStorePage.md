---
title: Adicionar Repositório de Arquivo do Front End
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.
ms.openlocfilehash: 10b07e5bbe075194e393fce8ac9a9c99bc85c01e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397024"
---
# <a name="add-front-end-file-store"></a>Adicionar Repositório de Arquivo de Front-end

É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.

> [!IMPORTANT]
> O compartilhamento de arquivos não pode ser localizado no servidor Edição Enterprise front-end, mas pode ser localizado em um Edição Standard servidor.

> [!IMPORTANT]
> É possível definir o compartilhamento de arquivo no Construtor de Topologia antes de criar o compartilhamento de arquivo, mas é necessário criar o compartilhamento de arquivo no local definido antes de publicar a topologia.

> [!IMPORTANT]
> Ao adicionar um pool de Front-Ends Enterprise ou servidor Standard Edition à sua topologia, o Construtor de Topologia precisa ser capaz de configurar o repositório de arquivos e configurar as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para o repositório de arquivos. Isso exige que, quando você executa o Construtor de Topologia para publicar a nova topologia, você é conectado com uma conta que tem permissões de controle total (leitura/gravação/modificação) para o compartilhamento de arquivo.

Para obter detalhes sobre o suporte [de](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) armazenamento para compartilhamentos de arquivos, consulte [File Armazenamento Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) na documentação de Suporte e SQL Server Posicionamento de Arquivos de Dados e Log na documentação de Implantação. Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) na documentação de Suporte. Para obter detalhes sobre como projetar a topologia para um pool Front-Ends Enterprise Edition, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) na documentação Implantação.