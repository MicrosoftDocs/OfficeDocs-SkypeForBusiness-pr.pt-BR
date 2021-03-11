---
title: Bloquear o acesso ao SharePoint para usuários específicos
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre como bloquear o acesso ao SharePoint para usuários específicos
ms.openlocfilehash: e3cda9d6443c41abc7dfa736be03555690a3b0f1
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615077"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Bloquear o acesso ao SharePoint para usuários específicos

A aplicação de qualquer política de Acesso Condicional (AC) do SharePoint no Microsoft 365 também se aplica ao Teams. No entanto, algumas organizações desejam bloquear o acesso aos arquivos do SharePoint (carregar, baixar, visualizar, editar, criar) e ainda permitir que seus funcionários usem clientes Web, móveis e da área de trabalho do Teams em dispositivos não gerenciados. De acordo com as regras de política AC, o bloqueio do Sharepoint também bloquearia o Teams. Este artigo explica como você pode contornar essa limitação e permitir que seus funcionários continuem usando o Teams enquanto bloqueia completamente o acesso aos arquivos armazenados no SharePoint.

> [!Note]
> O bloqueio ou limitação do acesso em dispositivos não gerenciados depende das políticas de acesso condicional do Microsoft Azure AD. Saiba mais sobre o [Licenciamento do Microsoft Azure AD](https://azure.microsoft.com/pricing/details/active-directory/). Para obter uma visão geral do acesso condicional no Microsoft Azure AD, confira [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Para obter informações sobre as políticas de acesso recomendadas do SharePoint Online, confira [Recomendações de política para proteger sites e arquivos do SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Se você limitar o acesso a dispositivos não gerenciados, os usuários de dispositivos gerenciados deverão usar um dos [sistemas operacionais e combinações de navegador com suporte](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), ou terão seu acesso limitado também.

Você pode bloquear ou limitar o acesso de:

- Usuários da organização ou apenas alguns usuários ou grupos de segurança.

- Todos os sites da organização ou apenas alguns deles.

Quando o acesso é bloqueado, os usuários verão uma mensagem de erro. O bloqueio de acesso ajuda a fornecer segurança e protege dados seguros. Quando o acesso é bloqueado, os usuários verão uma mensagem de erro.

1. Abra o Centro de Administração do SharePoint.

2. Expanda **Políticas** > **Políticas de Acesso**.

3. Na seção **Dispositivos não gerenciados**, selecione **Bloquear Acesso** e selecione **Salvar**.

   ![a seção Dispositivos não gerenciados para Políticas](media/no-sharepoint-access1.png)

4. Abra o portal do [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e acesse **Políticas de Acesso Condicional**.

    Você verá uma nova política criada pelo SharePoint semelhante a este exemplo:

    ![uma nova política chamada Usar restrições impostas pelo aplicativo para acesso ao navegador](media/no-sharepoint-access2.png)

5. Atualize a política para direcionar apenas a usuários ou a um grupo específicos.

    ![o Centro de Administração do Sharepoint com a seção Selecionar usuário destacada.](media/no-sharepoint-access2b.png)

  > [!Note]
> Configurar essa política impedirá seu acesso ao portal de administração do SharePoint. Recomendamos que você configure a política de exclusão e selecione os Administradores globais e do SharePoint.

6. Verificar se apenas o SharePoint está selecionado como Aplicativo na Nuvem de destino

    ![O SharePoint está selecionado como o aplicativo de destino.](media/no-sharepoint-access3.png)

7. Atualize as **Condições** para incluir clientes da área de trabalho também.

    ![aplicativos móveis e da área de trabalho em destaque.](media/no-sharepoint-access4.png)

8. Certifique-se de que **Conceder acesso** está habilitado

    ![conceder acesso está habilitado.](media/no-sharepoint-access5.png)

9. Certifique-se de que **Usar restrições impostas pelo aplicativo** está habilitado.

10. Habilite sua política e selecione **Salvar**.

    ![As restrições impostas pelo aplicativo estão habilitadas.](media/no-sharepoint-access6.png)

Para testar sua política, você precisa sair de qualquer cliente, como o aplicativo da área de trabalho do Teams ou o cliente de sincronização do OneDrive for Business e entrar novamente para ver a política funcionando. Se o seu acesso tiver sido bloqueado, você verá uma mensagem no Teams informando que o item pode não existir.

 ![Mensagem de item não encontrado.](media/access-denied-sharepoint.png)

No Sharepoint, você receberá uma mensagem de acesso negado.

![A mensagem de acesso negado.](media/blocked-access-warning.png)

## <a name="related-topics"></a>Tópicos relacionados

[Controle o acesso a dispositivos não gerenciados no SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
