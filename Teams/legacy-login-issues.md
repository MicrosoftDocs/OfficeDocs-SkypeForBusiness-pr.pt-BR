---
title: Problemas para receber mensagens e chamadas em sistemas herdadas no Teams
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
description: Solucionar problemas relacionados ao recebimento de mensagens e chamadas em sistemas herdadas
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085147"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas para receber mensagens e chamadas em sistemas herdadas
==============================================================

Os usuários podem ter problemas para receber mensagens ou chamadas se eles estão usando versões mais antigas do Teams ou se entraram com outros aplicativos.

## <a name="legacy-adu-setups"></a>Configurações herddas do ADU

 Se os usuários estiverem conectados a um computador ingressado no domínio e você **não quer que o nome de usuário seja preenchido previamente na tela de entrada do Teams**, os administradores poderão definir o seguinte registro do Windows para desativar o pré-preenchimento do nome do usuário (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.

Consulte [Entrar no Microsoft Teams usando a autenticação moderna](sign-in-teams.md) para obter mais informações.

## <a name="skype-token-revocation"></a>Revogação de token do Skype

Ao alterar/redefinir uma senha, os clientes mais antigos não receberão mensagens e chamadas por até uma hora. Para resolver esse problema, reinicie o aplicativo ou mova para clientes mais novos.


## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)