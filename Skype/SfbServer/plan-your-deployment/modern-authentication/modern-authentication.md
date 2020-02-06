---
title: Planejar para autenticação moderna no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Tópicos de planejamento para autenticação e autorização do Skype for Business Server, incluindo a integração com outros produtos
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815839"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutindo autenticação e autorização no Skype for Business

A autenticação e a autorização são conceitos relacionados, mas há um trabalho diferente para você (mas ambos são necessários). Colocar termos simples, Authenciation (Authn) depende dos segredos apenas que um usuário válido sabe ou tem e que pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações sobre o usuário que é verdadeira ou uma combinação dessas coisas usadas juntas. Authn é um processo para provar que você é quem diz ser.

Autorização (AuthZ) se preocupa com o que você tem acesso depois de comprovasse quem é você. Ele determina o que você tem permissão para ver, editar e acessar de outra forma. Por exemplo, você pode ter um poderoso acesso de administrador de conjunto de sites ao SharePoint Online, mas se você alternar para outra carga de trabalho online, como o Skype for Business Online, você pode ter privilégios para solucionar problemas de usuário, não alterar a configuração do servidor ou servidores. Em uma terceira carga de trabalho, como o Exchange Online, você pode ter apenas o acesso do usuário na média. A AuthZ verifica o que e quanto o acesso você tem a serviços/worloads, aplicativos, arquivos e outros dados.

Nossos exemplos envolvem Propriedades online, como o SharePoint e o Exchange Online, mas os processos de Authn e AuthZ trabalham no local e em um local híbrido da mesma maneira. Em última análise, as ferramentas como o AAD Connect e o ADFS se envolvem na história de autenticação interna e AuthZ sincronizando contas e senhas locais para o AD da nuvem (que é o Azure AD no caso do Office 365 ou do Azure) ou de intrusão no fluxo de AuthZ para que as credenciais do usuário não são sempre solicitadas, digamos, quando se alterna entre cargas de trabalho na nuvem, criando cenários de logon único. Mas elas não são, por si só, autorizadas ou AuthZ, apenas parte da mecânica.

Hoje em dia, muitas tecnologias consideram esses processos (Authn e AuthZ) serem um mecanismo e você ouvirá muitas referências ao processo de autenticação que também incluem autorização neles. É importante lembrar que a primeira etapa do acesso do usuário é Authn, provando que você é quem diz que você é e que a AuthZ usa o conhecimento de quem o usuário deve determinar o que ele ou ela tem acesso (como você verá com autorização aberta ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Tópicos de planejamento de autenticação e autorização

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planejando desativar métodos de autenticação herdados interna e externamente para a sua rede.](turn-on-modern-auth.md)

