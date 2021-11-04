---
title: Adicionar Repositório de Arquivo do Front End
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.
ms.openlocfilehash: 2427c5c90fb60d5a0ddef0ca428d336406e15c03
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739447"
---
# <a name="add-front-end-file-store"></a>Adicionar Repositório de Arquivo de Front-end

É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.

> [!IMPORTANT]
> O compartilhamento de arquivos não pode ser localizado no servidor Edição Enterprise front-end, mas pode ser localizado em um Edição Standard servidor.

> [!IMPORTANT]
> É possível definir o compartilhamento de arquivo no Construtor de Topologia antes de criar o compartilhamento de arquivo, mas é necessário criar o compartilhamento de arquivo no local definido antes de publicar a topologia.

> [!IMPORTANT]
> Ao adicionar um pool de Front-Ends Enterprise ou servidor Standard Edition à sua topologia, o Construtor de Topologia precisa ser capaz de configurar o repositório de arquivos e configurar as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para o repositório de arquivos. Isso exige que, quando você executa o Construtor de Topologia para publicar a nova topologia, você é conectado com uma conta que tem permissões de controle total (leitura/gravação/modificação) para o compartilhamento de arquivo.

Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Armazenamento Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) na documentação de Suporte e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) na documentação de Implantação. Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) na documentação de Suporte. Para obter detalhes sobre como projetar a topologia para um pool Front-Ends Enterprise Edition, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) na documentação Implantação.