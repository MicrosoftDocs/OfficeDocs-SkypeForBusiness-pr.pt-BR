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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5aeeea173a12e012a959b5fd37d802c6ea48c79
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37510748"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script do PowerShell para testar conexões do controlador de borda de sessão de roteamento direto

O cliente testador SIP é um exemplo de script do PowerShell que você pode usar para testar as conexões de SBC (controlador de borda de sessão de roteamento direto) no Microsoft Teams. Este script testa a funcionalidade básica de um tronco SIP (protocolo de iniciação de sessão) emparelhado ao cliente com roteamento direto.

O script envia um teste SIP para o executor do teste, aguarda o resultado e o apresenta em um formato legível por pessoas. Você pode usar esse script para testar os seguintes cenários:

- Chamadas de entrada e de saída
- Toque simultâneo
- Escalonamento de mídia
- Transferência consultiva

## <a name="download-the-script-and-documentation"></a>Baixar o script e a documentação

Baixe o [script e a documentação do cliente de teste SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/scripts/sip-tester-client/siptesterclient.zip?raw=true).