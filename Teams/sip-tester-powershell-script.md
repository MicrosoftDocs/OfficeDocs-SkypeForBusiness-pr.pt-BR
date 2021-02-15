---
title: Script do PowerShell para testar conexões de Controlador de Borda de Sessão de Roteamento Direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar as conexões do Controlador de Borda de Sessão de Roteamento Direto no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834271"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script do PowerShell para testar conexões de Controlador de Borda de Sessão de Roteamento Direto

O cliente de Teste SIP é um script do PowerShell de exemplo que você pode usar para testar conexões SBC (Controle de Borda de Sessão de Roteamento Direto) no Microsoft Teams. Este script testa a funcionalidade básica de um tronco SIP (Session Initiation Protocol) emparelhado ao cliente com Roteamento Direto.

O script envia um teste SIP ao corredor de teste, aguarda o resultado e o apresenta em um formato acessível. Você pode usar esse script para testar os seguintes cenários:

- Chamadas de entrada e saída
- Toque simultâneo
- Escalonamento de mídia
- Transferência consultiva

## <a name="download-the-script-and-documentation"></a>Baixar o script e a documentação

Baixe o [script e a documentação do cliente tester SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > O script do cliente SIP Tester dá suporte adal.ps versão 3.19.8.1. Um erro será retornado se uma versão posterior do adal.ps for usada.
  
  
