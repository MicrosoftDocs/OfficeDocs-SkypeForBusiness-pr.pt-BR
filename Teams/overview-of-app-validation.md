---
title: Visão geral da validação de aplicativos e teste de aplicativos pela Microsoft
description: Saiba mais sobre as diretrizes de validação de aplicativos do Teams com base nas políticas de certificação do marketplace. Entenda como a Microsoft garante que os aplicativos do Teams cumpram os altos padrões de privacidade e segurança.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d7d705d09dc9ded8ee2b831e41ed18921fbb7381
ms.sourcegitcommit: a4a65283e85d0c393c844dfd335df0d48e0e4105
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67314003"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Validação executada pela Microsoft para todos os aplicativos do Teams

A Microsoft exige que todos os aplicativos passem por uma validação obrigatória antes de serem listados na loja para uso final. Aplica-se a todos os aplicativos (exceto aplicativos personalizados) publicados na loja de Aplicativos do Teams. Além disso, a Microsoft incentiva fortemente os desenvolvedores de aplicativos a participarem de uma certificação opcional de aplicativos que indique controles avançados de conformidade, segurança e privacidade.

Todos os aplicativos são obrigatoriamente exigidos a aderirem às políticas de Certificação de Aplicativos da Microsoft. A equipe da loja do Teams realiza mais de 400 testes para garantir que os aplicativos sejam utilizáveis e cumpram altos padrões de privacidade e segurança.

Para conhecer as diretrizes detalhadas de validação às quais os desenvolvedores de aplicativos aderem, consulte [Diretrizes de validação para desenvolvedores](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). As diretrizes se baseiam nas [Políticas de certificação para aplicativos do Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> A validação e as verificações pela Microsoft não estão disponíveis para um aplicativo personalizado, pois ele é desenvolvido dentro da sua organização e só está disponível para membros da sua organização.

## <a name="app-validation-and-testing"></a>Validação e teste de aplicativos

Executamos mais de 400 casos de teste para cada aplicativo antes que ele seja disponibilizado na Teams Store. Os testes garantem funcionalidade, experiência do usuário e segurança adequadas, além de garantir que todos os aplicativos estejam em conformidade com as políticas de CMO listadas publicamente. A seguir estão alguns dos testes realizados pela equipe de validação de aplicativos da Microsoft para cada aplicativo antes de serem publicados:

* Certifique-se de que as permissões do Graph solicitadas pelo aplicativo são realmente as que a funcionalidade do aplicativo precisa e não quaisquer permissões extras. As permissões do Graph para aplicativos existentes são verificadas regularmente para garantir que nenhuma permissão extra seja necessária por um aplicativo.
* Os aplicativos que exigem que os usuários façam login têm uma opção de saída.
* Os desenvolvedores de todos os aplicativos passam por um processo de verificação detalhado no Microsoft Partner Center. A verificação inclui verificação de email, verificação de negócios e muito mais. Para saber mais sobre a publicação de aplicativos, consulte [Como os desenvolvedores criam uma conta no Partner Center](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guia de envio para desenvolvedores](/office/dev/store/add-in-submission-guide) e [Como os desenvolvedores publicam aplicativos](https://aka.ms/PublishToTeamsStore).
* Somente aplicativos de desenvolvedores verificados podem buscar permissões do Graph de usuários finais.
* Nenhum aplicativo pode baixar um arquivo executável.
* Os aplicativos são testados para não conter anúncios e promoções para outros aplicativos.
* Os aplicativos são testados para funcionarem adequadamente ao trabalho sem linguagem ofensiva, bots de ataque cibernético, spam ou conteúdo fraudulento.
* Todos os links em um aplicativo são funcionais e relacionados somente à oferta do aplicativo.
* Testamos e avaliamos regularmente todos os aplicativo publicados do Teams como parte das verificações de integridade da loja de aplicativos.
* A política de privacidade e os Termos de uso que abrangem aplicativos do Teams são fornecidos pelo desenvolvedor do aplicativo.
* Os detalhes de contato do desenvolvedor de aplicativo estão disponíveis na listagem da loja e em suas respectivas [páginas de atestado do fornecedor](/microsoft-365-app-certification/teams/teams-apps).

Além disso, a Microsoft incentiva os desenvolvedores de aplicativos a participarem do seu programa de conformidade, que é uma abordagem rigorosa de duas camadas para garantir a qualidade, a segurança e a conformidade do aplicativo. A loja do Teams tem centenas de aplicativos que vão além do cumprimento das diretrizes de validação já detalhadas e estão em conformidade com esses programas.

## <a name="related-article"></a>Artigo relacionado

* [Visão geral para administradores do programa de conformidade de aplicativos do Microsoft 365 ](overview-of-app-certification.md)
