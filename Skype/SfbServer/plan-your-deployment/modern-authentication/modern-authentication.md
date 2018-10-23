---
title: Planejar para autenticação moderna no Skype for Business
ms.author: tracyp
author: MSFTTracyP
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Tópicos de planejamento para autenticação e autorização para Skype para Business Server, incluindo a integração com outros produtos
ms.openlocfilehash: 218100a78b128b28188d7c0b49534a9eb8ff4a1d
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692715"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutir autenticação e autorização em Skype para negócios

Autenticação e autorização são conceitos relacionados, mas fazem trabalho diferentes por você (Embora ambos são necessários). Colocar em termos simples, authenciation (AuthN) depende segredos apenas um usuário válido reconheça ou possui e que pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações são verdadeiras sobre o usuário ou uma combinação dessas coisas usados juntos. AuthN é um processo de check-out provar que você é quem quer dizer que você está.

Autorização (AuthZ) diz respeito à qual você tenha acesso após comprovar que você está. Ele determina quais tenha sido permitido para ver, editar e acessar o contrário. Por exemplo, talvez você tenha poderosa acesso de administrador do conjunto de sites no SharePoint Online, mas se você alternar para outro workload online, como Skype para negócios Online, você pode ter os privilégios necessários para solucionar problemas do usuário, não altere a configuração do servidor ou servidores. Em uma carga de trabalho de terceira, como o Exchange Online, você somente pode ter acesso do usuário médio. AuthZ verifica qual e quanta acesso a serviços/worloads, aplicativos, arquivos e outros dados.

Nossos exemplos envolvem propriedades online como o SharePoint e o Exchange online, mas os processos de AuthN e AuthZ funcionam no local e em um local de híbrida da mesma maneira. Por fim, ferramentas como AAD conectar e ADFS se tornam envolvido no bloco AuthN e AuthZ por contas de sincronização local e senhas em nuvem do AD (que é o Azure AD no caso do Office 365 ou no Windows Azure) ou intruso no fluxo do AuthZ assim que um usuário com frequência não é solicitado para suas credenciais, dizer quando você alterna entre as cargas de trabalho na nuvem, criação de cenários de Single Sign-On. Mas não, eles próprios AuthN responsável ou AuthZ, apenas parte da mecânica.

Hoje, muitas tecnologias considerar esses processos (AuthN e AuthZ) para ser um mecanismo, e você ouvirá muitas referências ao processo de autenticação que também incluem autorização neles. É importante lembrar que a primeira etapa no acesso do usuário é AuthN, comprovar que você é quem quer dizer que você está, e que AuthZ usa o conhecimento do que o usuário é determinar o que ele tem acesso ao (conforme você verá com autorização aberta ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Tópicos de planejamento de autorização e autenticação

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planejamento desativar os métodos de autenticação Legacy interna e externamente à sua rede.](turn-on-modern-auth.md)

