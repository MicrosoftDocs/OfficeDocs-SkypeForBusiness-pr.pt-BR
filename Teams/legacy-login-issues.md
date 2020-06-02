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
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="75906-103">Problemas ao receber mensagens e chamadas em sistemas herdados</span><span class="sxs-lookup"><span data-stu-id="75906-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="75906-104">Os usuários podem ter problemas para receber mensagens ou chamadas se estiverem usando versões mais antigas do teams ou se tiverem feito logon com outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="75906-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="75906-105">Configurações herdadas do ADU</span><span class="sxs-lookup"><span data-stu-id="75906-105">Legacy ADU setups</span></span>

 <span data-ttu-id="75906-106">Se os usuários estiverem conectados a um computador ingressado no domínio e você **não quer que o nome de usuário seja preenchido previamente na tela de entrada do Teams**, os administradores poderão definir o seguinte registro do Windows para desativar o pré-preenchimento do nome do usuário (UPN):</span><span class="sxs-lookup"><span data-stu-id="75906-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="75906-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="75906-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="75906-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="75906-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="75906-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="75906-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="75906-110">Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.</span><span class="sxs-lookup"><span data-stu-id="75906-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="75906-111">Consulte [entrar no Microsoft Teams usando a autenticação moderna](sign-in-teams.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="75906-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="75906-112">Revogação de token do Skype</span><span class="sxs-lookup"><span data-stu-id="75906-112">Skype token revocation</span></span>

<span data-ttu-id="75906-113">Ao alterar/redefinir uma senha, os clientes mais antigos não receberão mensagens e chamadas para até uma hora.</span><span class="sxs-lookup"><span data-stu-id="75906-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="75906-114">Para solucionar esse problema, reinicie o aplicativo ou mova-se para clientes mais recentes.</span><span class="sxs-lookup"><span data-stu-id="75906-114">To resolve this issue, either restart the app or move to newer clients.</span></span>
