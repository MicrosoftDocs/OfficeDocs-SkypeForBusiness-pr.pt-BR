---
title: Adicionar Repositório de Arquivo Diretor
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
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: 4c68e592568f160575433d5b4f772eadf8c81a2e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215532"
---
# <a name="add-director-file-store"></a>Adicionar Repositório de Arquivo Diretor

Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.

> [!IMPORTANT]
> Quando você adiciona Diretores a uma topologia, a publicação da topologia necessita de acesso apropriado para configurar o repositório de arquivos e as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para repositório de arquivos. Isso exige que você esteja conectado com uma conta que tenha permissões totais de controle (ler/gravar/modificar) para o compartilhamento de arquivos, quando executar o Construtor de Topologia e publicar a nova topologia.

Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação de suporte e [dados do SQL Server e posicionamento de arquivos de log](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação. Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de Suporte. Para maiores detalhes sobre como projetar a topologia para Diretores, consulte [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) na documentação de Implantação.


