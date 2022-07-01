---
title: Script do PowerShell para testar conexões do Controlador de Borda da Sessão de Roteamento Direto
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar as conexões do Controlador de Borda da Sessão de Roteamento Direto no Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564129"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script do PowerShell para testar conexões do Controlador de Borda da Sessão de Roteamento Direto

O cliente do Testador SIP é um script do PowerShell de exemplo que você pode usar para testar conexões SBC (Controlador de Borda de Sessão de Roteamento Direto) no Microsoft Teams. Esse script testa a funcionalidade básica de um tronco SIP (Protocolo de Iniciação de Sessão) emparelhado com o cliente com o Roteamento Direto.

O script envia um teste SIP para o executor de teste, aguarda o resultado e o apresenta em um formato legível por humanos. Você pode usar esse script para testar os seguintes cenários:

- Chamadas de saída e de entrada
- Anel simultâneo
- Escalonamento de mídia
- Transferência consultiva

## <a name="download-the-script-and-documentation"></a>Baixar o script e a documentação

Baixe o script [e a documentação do cliente do Testador SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > O script de cliente do Testador SIP dá suporte adal.ps versão 3.19.8.1. Um erro será retornado se uma versão posterior do adal.ps for usada.
  
  
