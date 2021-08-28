---
title: Instalar Invocação do Repositório de Configuração Local (Configuração)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para começar a instalação do banco de dados que armazenará a cópia somente leitura local do armazenamento de Gerenciamento Central, selecione entre recuperar a configuração definida publicada usando o Construtor de Topologia no armazenamento de Gerenciamento Central já instalado e configurado ou lendo a configuração definida de outras mídias. Para um computador que está na rede interna da sua organização, selecione Recuperar configuração automaticamente no Armazenamento de Gerenciamento Central.
ms.openlocfilehash: 1c5b90e0758c892a42286637fa30a6739932bdfb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635475"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar Invocação do Repositório de Configuração Local (Configuração)
 
Para começar a instalação do banco de dados que armazenará a cópia somente leitura local do armazenamento de Gerenciamento Central, selecione entre recuperar a configuração definida publicada usando o Construtor de Topologia no armazenamento de Gerenciamento Central já instalado e configurado ou lendo a configuração definida de outras mídias. Para um computador que está na rede interna da sua organização, selecione Recuperar configuração automaticamente **do Armazenamento de Gerenciamento Central**.
  
Se você estiver instalando uma réplica do repositório de Gerenciamento Central em um Servidor de Borda, selecione para ler a cópia exportada do documento de configuração da mídia portátil, como uma unidade flash USB, disco rígido USB, CD-ROM ou outra mídia. 
  
> [!IMPORTANT]
> Se você estiver instalando o armazenamento de Configuração Local em um Servidor de Borda, as informações de configuração devem estar em um formato que foi exportado do armazenamento de Gerenciamento Central executando o cmdlet Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Após ter selecionado a opção adequada, clique em **Próximo**.
  

