---
title: Solucionar problemas do Career Coach para o Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como solucionar problemas comuns no Career Coach do Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024128"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Solucionar problemas do Career Coach para o Microsoft Teams

Este artigo é para administradores de TI de nível superior que precisam solucionar problemas de Career Coach para o Microsoft Teams.

Abaixo estão os problemas comuns e as etapas de resolução que os administradores de TI podem seguir com o Career Coach.

## <a name="missing-required-configuration-data"></a>Dados de configuração necessários ausentes

Se você vir "O Career Coach está sendo configurado para uso em breve" na experiência do Career Coach, todos os dados de configuração necessários não **foram adicionados**.

As **seções a seguir devem ser concluídas antes** que o Career Coach possa ser usado:

- [Marca e preferências](career-coach-set-up-steps.md#brand-and-preferences)
- [Conexão do LinkedIn](career-coach-set-up-steps.md#linkedin-connection)
- [Catálogo de cursos](career-coach-set-up-steps.md#course-catalog)
- [Campos de estudo](career-coach-set-up-steps.md#fields-of-study)

Consulte o status [de configuração do Career Coach](career-coach-set-up-steps.md#configuration-status) para ver quais configurações precisam ser concluídas.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Formatação incorreta do catálogo de cursos ou campos de dados de estudo

Os CSVs para o catálogo de cursos e o campo de estudo têm formatos obrigatórios e um tamanho máximo de 18 MB.

Consulte o esquema do documento do [catálogo de cursos](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) do Career Coach e os campos De coach de carreira do esquema de documento de [estudo](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) para garantir a configuração adequada.

Além disso, um arquivo de catálogo de cursos não deve ter mais de 15.000 linhas para garantir o processamento bem-sucedido.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Campos ausentes nas páginas de configurações do Career Coach

As páginas de configurações do Career Coach têm campos obrigatórios. Se os campos necessários não forem concluídos, a página não enviará.

Talvez você não veja uma mensagem de aviso e a página não será enviada.

O envio é bem-sucedido quando você vê uma faixa verde na parte superior da página.

## <a name="setup-policy-changes-arent-complete"></a>As alterações da política de instalação não foram concluídas

Se o Career Coach não estiver sendo exibido no Microsoft Teams para usuários, as alterações da política de configuração poderão ainda não ter efeito. O Career Coach não será instalado e fixado para usuários no Microsoft Teams até que as alterações da política de configuração entre em vigor. As alterações de política podem levar algumas horas para entrar em vigor.

No entanto, o Career Coach pode ser instalado diretamente da loja de aplicativos do Microsoft Teams.

- Se os usuários não puderem encontrar o Career Coach na loja de aplicativos do Microsoft Teams, examine as políticas de permissão do aplicativo e verifique se o Career Coach não é um aplicativo bloqueado.
- O Career Coach é um aplicativo da Microsoft e é uma prática recomendada permitir aplicativos da Microsoft por políticas de permissão. Saiba mais sobre como [configurar políticas de permissão](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>A inicialização do Career Coach não foi concluída

Você pode encontrar o seguinte erro: "Não é possível recuperar as configurações do aplicativo. Tente novamente. Se você continuar com problemas, entre em contato com o atendimento ao cliente da Microsoft."

Verifique o **status de Provisionamento de Serviço** na página [de configurações do Career Coach](career-coach-set-up-steps.md#career-coach-settings-status).

Se o locatário ainda estiver sendo inicializado, aguarde 15 minutos e tente novamente. Abra um tíquete de suporte se você ainda receber o erro.
