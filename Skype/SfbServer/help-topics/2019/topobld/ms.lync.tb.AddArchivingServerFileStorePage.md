---
title: Adicionar Repositório de Arquivo de Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou especificar um novo compartilhamento de arquivos. Basta especificar o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deverá ser localizado, assim como o nome de sua pasta.
ms.openlocfilehash: 568d7254b4af28271befcf51811ff3659780fe3f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689696"
---
# <a name="add-archiving-server-file-store"></a>Adicionar Repositório de Arquivo de Servidor de Arquivamento

Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou especificar um novo compartilhamento de arquivos. Basta especificar o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deverá ser localizado, assim como o nome de sua pasta.

> [!IMPORTANT]
> Você pode definir um compartilhamento de arquivos no Construtor de Topologia antes de criar o compartilhamento de arquivos, mas você deve criar um compartilhamento de arquivos no local definido antes de publicar a topologia. > ao adicionar um servidor de arquivamento à sua topologia, o construtor de topologias deve ser capaz de configurar o repositório de arquivos de arquivamento e configurar listas de controle de acesso discricional (DACLs) no compartilhamento de arquivos a ser usado para o repositório de arquivos. Isso exige que, quando executar o Construtor de Topologias para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) sobre o compartilhamento de arquivos.

Para obter detalhes sobre o suporte ao armazenamento para compartilhamentos de arquivo, consulte [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação Sistemas de suporte e [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação Implantação. Para obter detalhes sobre colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação Sistemas de suporte.


