---
title: Adicionar Repositório de Arquivo Diretor
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: 98e5362f401e28fab2b8e416f5f57b2798581004
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990769"
---
# <a name="add-director-file-store"></a>Adicionar Repositório de Arquivo Diretor
 
Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
  
> [!IMPORTANT]
> Quando você adiciona Diretores a uma topologia, a publicação da topologia requer um acesso apropriado para configurar o repositório de arquivos e as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para o repositório de arquivos. Quando executar o Construtor de Topologias e publicar a nova topologia, porém, você tem que estar conectado a uma conta que tenha permissões totais de controle (ler/gravar/modificar) sobre o compartilhamento de arquivos. 
  
Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [Suporte de armazenamento do arquivo](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação de suporte e [localização do arquivo de Log e de dados do SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação. Para obter detalhes sobre a colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de suporte. Para obter detalhes sobre como projetar a topologia para diretores, consulte [Define um diretor único no construtor de topologia](http://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) na documentação de implantação.
  

