---
title: Script do PowerShell para testar conexões do controlador de borda de sessão de roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar as conexões de controlador de borda de sessão de roteamento direto no Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344bf59d401e43c40c6f643b334c2f34311d6cbe
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116687"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script do PowerShell para testar conexões do controlador de borda de sessão de roteamento direto

O cliente testador SIP é um exemplo de script do PowerShell que você pode usar para testar as conexões de SBC (controlador de borda de sessão de roteamento direto) no Microsoft Teams. Este script testa a funcionalidade básica de um tronco SIP (protocolo de iniciação de sessão) emparelhado ao cliente com roteamento direto.

O script envia um teste SIP para o executor do teste, aguarda o resultado e o apresenta em um formato legível por pessoas. Você pode usar esse script para testar os seguintes cenários:

- Chamadas de entrada e de saída
- Toque simultâneo
- Escalonamento de mídia
- Transferência consultiva

## <a name="download-the-script-and-documentation"></a>Baixar o script e a documentação

Baixe o [script e a documentação do cliente de teste SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > O script do cliente testador SIP suporta apenas a versão adal.ps do 3.19.8.1. Um erro será retornado se uma versão mais recente do adal.ps for usada.
  
  
