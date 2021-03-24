---
title: Adicionar Repositório de Arquivo Diretor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: 56fb33653f2f463e9b336ae447a1c665680ed6df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100137"
---
# <a name="add-director-file-store"></a>Adicionar Repositório de Arquivo Diretor

Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.

> [!IMPORTANT]
> Quando você adiciona Diretores a uma topologia, a publicação da topologia necessita de acesso apropriado para configurar o repositório de arquivos e as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para repositório de arquivos. Isso exige que você esteja conectado com uma conta que tenha permissões totais de controle (ler/gravar/modificar) para o compartilhamento de arquivos, quando executar o Construtor de Topologia e publicar a nova topologia.

Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) na documentação de Suporte e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) na documentação de Implantação. Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) na documentação de Suporte. Para maiores detalhes sobre como projetar a topologia para Diretores, consulte [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) na documentação de Implantação.