---
title: Adicionar Repositório de Arquivos de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivos especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivos será localizado e um nome de pasta para o novo compartilhamento de arquivo.
ms.openlocfilehash: 1aebf332543bb639052beb04b91e58385cac82d5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263799"
---
# <a name="add-front-end-file-store"></a>Adicionar Repositório de Arquivos de Front-End

É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivos especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivos será localizado e um nome de pasta para o novo compartilhamento de arquivo.

> [!IMPORTANT]
> O compartilhamento de arquivos não pôde ser localizado no Servidor de Front-Ends Enterprise Edition, mas foi localizado em um servidor Standard Edition.

> [!IMPORTANT]
> Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deverá criá-lo no local que você definiu antes de publicar a topologia.

> [!IMPORTANT]
> Ao adicionar um pool de Front-Ends Enterprise ou servidor Standard Edition à sua topologia, o Construtor de Topologias tem que instalar o repositório de arquivos e configurar as listas de controle de acesso condicional (DACL) no compartilhamento de arquivos a ser usado para o repositório de arquivos. Isso exige que você esteja conectado com uma conta que tenha permissões de controle total (leitura/gravação/modificação) sobre o compartilhamento de arquivos quando executar o Construtor de Topologias para publicar a nova topologia.

Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [Suporte de armazenamento do arquivo](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação de suporte e [localização do arquivo de Log e de dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação. Para obter detalhes sobre a colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de suporte. Para obter detalhes sobre como projetar a topologia para um pool de Front End do Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de implantação.


