---
title: Adicionar Repositório de Arquivo de Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou pode especificar um compartilhamento de arquivos novo, especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deve estar localizado e um nome de pasta para ele.
ms.openlocfilehash: 22f7de704b3d7a611d4601df4c14ed75f7466c1c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217422"
---
# <a name="add-archiving-server-file-store"></a>Adicionar Repositório de Arquivo de Servidor de Arquivamento

Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou pode especificar um compartilhamento de arquivos novo, especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deve estar localizado e um nome de pasta para ele.

> [!IMPORTANT]
> Você pode definir um compartilhamento de arquivos no Construtor de Topologia antes de criar o compartilhamento de arquivos, mas você deve criar um compartilhamento de arquivos no local definido antes de publicar a topologia. > quando você adicionar um servidor de arquivamento à sua topologia, o construtor de topologias deverá ser capaz de configurar o repositório de arquivos de arquivamento e configurar listas de controle de acesso discricional (DACLs) no compartilhamento de arquivos a serem usados para o repositório de arquivos. Isso exige que, quando executar o Construtor de Topologia para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos.

Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação de suporte e [dados do SQL Server e posicionamento de arquivos de log](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação. Para obter detalhes sobre colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de Suporte.


