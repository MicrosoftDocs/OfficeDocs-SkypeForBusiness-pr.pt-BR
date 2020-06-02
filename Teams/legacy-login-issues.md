---
title: Problemas ao receber mensagens e chamadas em sistemas herdados no Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
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
description: Solucionar problemas relacionados ao recebimento de mensagens e chamadas em sistemas herdados
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489153"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas ao receber mensagens e chamadas em sistemas herdados
==============================================================

Os usuários podem ter problemas para receber mensagens ou chamadas se estiverem usando versões mais antigas do teams ou se tiverem feito logon com outros aplicativos.

## <a name="legacy-adu-setups"></a>Configurações herdadas do ADU

 Se os usuários estiverem conectados a um computador ingressado no domínio e você **não quer que o nome de usuário seja preenchido previamente na tela de entrada do Teams**, os administradores poderão definir o seguinte registro do Windows para desativar o pré-preenchimento do nome do usuário (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.

Consulte [entrar no Microsoft Teams usando a autenticação moderna](sign-in-teams.md) para obter mais informações.

## <a name="skype-token-revocation"></a>Revogação de token do Skype

Ao alterar/redefinir uma senha, os clientes mais antigos não receberão mensagens e chamadas para até uma hora. Para solucionar esse problema, reinicie o aplicativo ou mova-se para clientes mais recentes.
