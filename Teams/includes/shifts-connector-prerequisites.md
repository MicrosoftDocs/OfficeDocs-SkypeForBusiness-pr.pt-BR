---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593628"
---
Antes de começar, certifique-se de ter os seguintes pré-requisitos:

- Blue Yonder WFM versão 2020.3, 2021.1 ou 2021.2.

    > [!NOTE]
    > Se você tiver Blue Yonder WFM 2020.3 ou 2021.1, aplique o patch 2020.3.0.4 ou 2021.1.0.3. Esse patch corrige um problema em que os usuários receberão uma mensagem de erro persistente em Shifts. Ele também corrige um problema que impede que os usuários atualizá-los em Shifts.

- Seu nome de conta de serviço WFM do Blue Yonder e URLs de senha e serviço:

    - URL de autenticação federada
    - URL de autenticação de cookie
    - URL de autoatend nome do funcionário
    - URL da API da Web de varejo
    - URL da API do Gerenciador de Sites
    - URL da API de Administração

    Se você não tiver essas informações, entre em contato com o suporte do Blue Yonder. A conta é criada no nível da empresa raiz por um administrador da empresa Blue Yonder. Ele deve ter Acesso à API, Administrador de Cliente e Acesso ao Gerenciador da Loja. A conta e a senha são necessárias para criar uma conexão.
- A autenticação SSO federada está habilitada em seu ambiente WFM do Blue Yonder. Entre em contato com o suporte do Blue Yonder para garantir que o SSO federado está habilitado. Eles precisarão das seguintes informações:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` onde {tenantId} é seu tenantId
     - proxyHeader: X-MS-AuthToken

- Pelo menos uma equipe é configurada em Teams.
- Você adicionou sua Microsoft 365 do sistema como proprietário da equipe a todas as equipes que deseja mapear.</br> [Crie essa conta no Microsoft 365](/microsoft-365/admin/add-users/add-users) e atribua a ela uma Microsoft 365 de usuário. Em seguida, adicione a conta como proprietário de equipe a todas as equipes que você deseja mapear. O conector Shifts usa essa conta ao sincronizar as alterações shifts do WFM do Blue Yonder.

    Recomendamos que você crie uma conta especificamente para essa finalidade e não use sua conta de usuário.