---
title: Script do PowerShell para testar conexões do Controlador de Borda de Sessão de Roteamento Direto
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar conexões de Controlador de Borda de Sessão de Roteamento Direto Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: acba1d06debc9a0e06ee6636e14ee5cbf15bd90f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774401"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script do PowerShell para testar conexões do Controlador de Borda de Sessão de Roteamento Direto

O cliente do Testador SIP é um script do PowerShell de exemplo que você pode usar para testar conexões SBC (Direct Routing Session Border Controller) no Microsoft Teams. Este script testa a funcionalidade básica de um tronco SIP (Protocolo de Iniciação de Sessão) emparelhado ao cliente com Roteamento Direto.

O script envia um teste SIP para o testador, aguarda o resultado e o apresenta em um formato acessível para humanos. Você pode usar esse script para testar os seguintes cenários:

- Chamadas de saída e de entrada
- Anel simultâneo
- Escalonamento de mídia
- Transferência consultiva

## <a name="download-the-script-and-documentation"></a>Baixar o script e a documentação

Baixe o [script e a documentação do cliente do Testador SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > O script de cliente do testador SIP só dá suporte adal.ps versão 3.19.8.1. Um erro será retornado se uma versão posterior do adal.ps for usada.
  
  
