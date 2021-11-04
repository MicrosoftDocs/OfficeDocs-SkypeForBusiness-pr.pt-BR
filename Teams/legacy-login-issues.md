---
title: Problemas de recebimento de mensagens e chamadas em sistemas herdado em Teams
ms.reviewer: ''
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Solucionar problemas relacionados ao recebimento de mensagens e chamadas em sistemas herdadas
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb36f4be70b174a324f017b1e52529f457e83f36
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768299"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas de recebimento de mensagens e chamadas em sistemas herdadas

Os usuários podem ter problemas para receber mensagens ou chamadas se eles estão usando versões mais antigas Teams ou se fizeram logo in-lo com outros aplicativos.

## <a name="legacy-adu-setups"></a>Configurações herdas do ADU

 Se os usuários estiverem conectados a um computador ingressado no domínio e você **não quer que o nome de usuário seja preenchido previamente na tela de entrada do Teams**, os administradores poderão definir o seguinte registro do Windows para desativar o pré-preenchimento do nome do usuário (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.

Consulte [Entrar para Microsoft Teams autenticação moderna](sign-in-teams.md) para obter mais informações.

## <a name="skype-token-revocation"></a>Skype revogação de token

Ao alterar/redefinir uma senha, os clientes mais antigos não receberão mensagens e chamadas por até uma hora. Para resolver esse problema, reinicie o aplicativo ou mova-se para clientes mais novos.


## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)