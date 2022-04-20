---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593628"
---
Antes de começar, verifique se você tem os seguintes pré-requisitos:

- Blue Yonder WFM versão 2020.3, 2021.1 ou 2021.2.

    > [!NOTE]
    > Se você tiver o Blue Yonder WFM 2020.3 ou 2021.1, aplique o patch 2020.3.0.4 ou 2021.1.0.3. Esse patch corrige um problema em que os usuários obtêm uma mensagem de erro persistente no Shifts. Ele também corrige um problema que impede que os usuários atualizá-los no Shifts.

- Seu nome de conta de serviço blue yonder WFM, senha e URLs de serviço:

    - URL de autenticação federada
    - URL de autenticação de cookie
    - URL de autoatendimento do funcionário
    - URL da API Web de varejo
    - URL da API do gerenciador de sites
    - URL da API de Administração

    Se você não tiver essas informações, entre em contato com o suporte do Blue Yonder. A conta é criada no nível da empresa raiz por um administrador corporativo do Blue Yonder. Ele deve ter acesso à API, ao administrador do cliente e ao Gerenciador da Loja. A conta e a senha são necessárias para criar uma conexão.
- A autenticação de SSO federado está habilitada em seu ambiente WFM do Blue Yonder. Entre em contato com o suporte do Blue Yonder para garantir que o SSO federado esteja habilitado. Eles precisarão das seguintes informações:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` em que {tenantId} é sua tenantId
     - proxyHeader: X-MS-AuthToken

- Pelo menos uma equipe está configurada em Teams.
- Você adicionou sua Microsoft 365 do sistema como proprietário da equipe a todas as equipes que deseja mapear.</br> [Crie essa conta no Microsoft 365](/microsoft-365/admin/add-users/add-users) e atribua a ela uma licença Microsoft 365 usuário. Em seguida, adicione a conta como proprietário da equipe a todas as equipes que você deseja mapear. O conector do Shifts usa essa conta ao sincronizar alterações de Shifts do WFM Do Remetente Azul.

    Recomendamos que você crie uma conta especificamente para essa finalidade e não use sua conta de usuário.