---
title: Adicionar Repositório de Arquivo de Servidor de Arquivamento
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou especificar um novo compartilhamento de arquivos. Basta especificar o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deverá ser localizado, assim como o nome de sua pasta.
ms.openlocfilehash: 9d32871fbfdd60f3c417be3d6f60a06192474df1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260542"
---
# <a name="add-archiving-server-file-store"></a>Adicionar Repositório de Arquivo de Servidor de Arquivamento

Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou especificar um novo compartilhamento de arquivos. Basta especificar o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deverá ser localizado, assim como o nome de sua pasta.

> [!IMPORTANT]
> Você pode definir um compartilhamento de arquivos no Construtor de Topologia antes de criar o compartilhamento de arquivos, mas você deve criar um compartilhamento de arquivos no local definido antes de publicar a topologia. > Quando você adiciona um servidor de arquivamento à sua topologia, construtor de topologia deve ser capaz de instalar o repositório de arquivos de arquivamento e configurar listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a serem usados para o repositório de arquivos. Isso exige que, quando executar o Construtor de Topologias para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) sobre o compartilhamento de arquivos.

Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [Suporte de armazenamento do arquivo](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação de suporte e [localização do arquivo de Log e de dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação. Para obter detalhes sobre a colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de suporte.


