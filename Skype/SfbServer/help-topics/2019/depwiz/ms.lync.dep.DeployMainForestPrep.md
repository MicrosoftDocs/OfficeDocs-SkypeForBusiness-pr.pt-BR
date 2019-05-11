---
title: Preparar Floresta Atual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar a floresta do Active Directory Domain Services, você deve com êxito estender o esquema, conforme descrito no tópico Running Schema Preparation e certifique-se de que o esquema foi replicado.
ms.openlocfilehash: 5cf217e054f513b8e3fcbc203cf4c0d76719e7cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893690"
---
# <a name="prepare-current-forest"></a>Preparar Floresta Atual

Para preparar a floresta do Active Directory Domain Services, você deve com êxito estender o esquema, conforme descrito no tópico [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)e certifique-se de que o esquema foi replicado.

Depois de atender a esses pré-requisitos, você pode começar a **Etapa 3: preparar floresta atual**. Para preparar a floresta, faça logon em um computador na raiz da floresta como membro de Admins. do Domínio na raiz da floresta, ou como membro de Administradores de Empresa na floresta que você está preparando.

1. No Assistente de Implantação em **Etapa 3: preparar floresta atual**, clique em **Executar**.

2. Na página **Preparar Floresta**, clique em **Próximo**.

    > [!NOTE]
    > A preparação da floresta permite que você escolha onde colocar os grupos universais do Skype para Business Server. Escolha um local que atenda aos requisitos de sua organização.

3. Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**. Certifique-se de que não haja erros. Revise os avisos a fim de determinar se são esperados e normais para sua infraestrutura.

4. Na coluna **ação** no log, expanda **A preparação da floresta**, procure uma ** \<sucesso\> ** resultado da execução do final de cada tarefa para verificar que a preparação da floresta foi concluída com êxito, feche o log e clique em **Concluir **.

5. Aguarde a conclusão da replicação do Active Directory Domain Services ou force a replicação para todos os controladores de domínio listados no snap-in **serviços e Sites do Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para fazer com que a replicação nos sites ocorra dentro de minutos.

    > [!TIP]
    > Se você precisar revisar os arquivos de log são criados pelo Skype para o Assistente de implantação de servidor de negócios, você pode encontrá-los no computador onde o Assistente de implantação foi executado, no diretório de usuários do usuário Active Directory Domain Services que executou a etapa. Por exemplo, se o usuário logado como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp


