---
title: Solucionar problemas de treinador de carreira para equipes de Microsoft
author: DaniEASmith
ms.author: danismith
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como solucionar problemas comuns no Career Coach for Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c00837c40fe405ab4d9d608326a12567843c8bb
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242445"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Solucionar problemas de treinador de carreira para equipes de Microsoft

Este artigo é para administradores de TI de educação que precisam solucionar problemas do Career Coach para Microsoft Teams.

Abaixo estão os problemas comuns e as etapas de resolução que os administradores de TI podem tomar com o Career Coach.

## <a name="missing-required-configuration-data"></a>Dados de configuração necessários ausentes

Se você vir "O Career Coach está sendo configurado para você usar em breve" na experiência do Career Coach, **todos os dados de configuração necessários não foram adicionados**.

Sua instituição deve ter a [conexão do LinkedIn](career-coach-set-up-steps.md#linkedin-connection-required) totalmente configurada.

Referencie o [status de configuração do Career Coach](career-coach-set-up-steps.md#configuration-status) para ver quais configurações precisam ser concluídas.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Formatação incorreta do catálogo de cursos ou campos de dados de estudo

CSVs para catálogo de cursos e campo de estudo têm formatos necessários e um tamanho máximo de 18 MB.

Referencie o [esquema de documentos do catálogo de cursos](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) do Career Coach e os [campos do Career Coach do esquema de documentos de estudo](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) para garantir a configuração adequada.

Além disso, um arquivo de catálogo de cursos não deve ter mais de 15.000 linhas para garantir o processamento bem-sucedido.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Campos ausentes nas páginas de configurações do Career Coach

As páginas de configurações do Career Coach têm campos necessários. Se os campos necessários não forem concluídos, a página não será enviada.

Talvez você não veja uma mensagem de aviso e a página não será enviada.

O envio é bem-sucedido quando você vê uma faixa verde na parte superior da página.

## <a name="setup-policy-changes-arent-complete"></a>As alterações de política de instalação não estão concluídas

Se o Career Coach não estiver sendo exibido no Microsoft Teams para usuários, as alterações na política de configuração podem não ter entrado em vigor ainda. O Career Coach não será instalado e fixado para usuários no Microsoft Teams até que as alterações na política de configuração entrem em vigor. As alterações na política podem levar algumas horas para entrar em vigor.

No entanto, o Career Coach pode ser instalado diretamente na loja de aplicativos Microsoft Teams.

- Se os usuários não conseguirem encontrar o Career Coach na loja de aplicativos do Microsoft Teams, examine as políticas de permissão do aplicativo e verifique se o Career Coach não é um aplicativo bloqueado.
- O Career Coach é um aplicativo Microsoft e é uma prática recomendada permitir Microsoft aplicativos por políticas de permissão. Saiba mais sobre [como configurar políticas de permissão](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>A inicialização do Career Coach não está concluída

Você pode encontrar o seguinte erro: "Não podemos recuperar as configurações do aplicativo. Tente novamente. Se você continuar com problemas, entre em contato com Microsoft suporte ao cliente".

Verifique o **status do Provisionamento de Serviços** na [página Configurações do Coach de Carreira](career-coach-set-up-steps.md#career-coach-settings-status).

Se o locatário ainda estiver sendo inicializado, aguarde 15 minutos e tente novamente. Abra um tíquete de suporte se você ainda receber o erro.
