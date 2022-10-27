---
title: Gerenciar o acesso aos aplicativos do Teams no Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/24/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como gerenciar o acesso aos aplicativos do Teams no Microsoft 365.
ms.openlocfilehash: 01aee1ebd59b52f05db36303d60358b86b95cf84
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738797"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gerenciar o acesso aos aplicativos do Teams no Microsoft 365

Os desenvolvedores de aplicativos podem aprimorar seus aplicativos do Microsoft Teams para funcionar no Outlook e Office.com, além do aplicativo que funciona no Teams. Os usuários finais podem usar os aplicativos aprimorados no Teams, no Microsoft Outlook e no Microsoft Office.com. Atualmente, apenas os usuários finais na [versão direcionada](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) podem exibir e usar esses aplicativos específicos no Teams, Outlook e Office.com. Uma notificação sobre essa alteração está disponível no [centro de mensagens](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280).

## <a name="manage-users-access-to-the-enhanced-apps"></a>Gerenciar o acesso do usuário aos aplicativos aprimorados

A experiência de administrador existente do Teams se aplica para controlar o acesso a esses aplicativos. Os administradores do Teams usam o centro de administração do Teams para gerenciar o acesso ao aplicativo. Como administrador do Teams, você pode permitir que usuários finais específicos usem os aplicativos aprimorados ou gerenciem o acesso aos aplicativos aprimorados no Teams, no Outlook e no Office.com.

Para uso no Outlook e Office.com, um aplicativo aprimorado continua usando as permissões existentes concedidas no Teams. Não há nenhuma alteração nas permissões do aplicativo aprimorado. Os usuários que instalaram suplementos existentes no mercado do mesmo aplicativo no Outlook e no Office continuarão a usar esse aplicativo. Os suplementos não são aplicativos do Teams e os administradores do Teams não podem controlar o acesso.

Os administradores do Office Apps podem entrar em contato com o administrador global ou o administrador do Teams para gerenciar o acesso dos aplicativos aprimorados. Para obter mais informações, confira [funções de administrador no Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true).

Você pode controlar o acesso do usuário final usando os métodos a seguir.

| Opções para gerenciar o acesso |Portal|Administrador global|Administrador de Teams|
|--|---|---|--|
| Somente os usuários finais do lançamento direcionado podem acessar o novo aplicativo. Mova os usuários para o lançamento padrão. Consulte [Configurar as opções do lançamento direcionado ou padrão](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centro de administração do Microsoft 365 | Sim | Não |
| Gerencie o acesso ao novo aplicativo para usuários finais específicos. Consulte [Adicionar uma política de permissão personalizada](teams-app-permission-policies.md#create-an-app-permission-policy) [e atribua a política personalizada a um usuário](policy-assignment-overview.md). | Centro de administração do Teams | Sim | Sim |
| Gerencie o acesso aos novos aplicativos para todos os usuários finais em toda a organização. Consulte [Permitir ou bloquear aplicativos](manage-apps.md#allow-and-block-apps). | Centro de administração do Teams | Sim | Sim |

> [!NOTE]
> É recomendável usar [a opção do lançamento padrão](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) para gerenciar o acesso do usuário final. As outras opções removem o acesso do usuário final e não poderão mais usar o aplicativo existente no Teams.

## <a name="list-of-enhanced-apps"></a>Lista de aplicativos aprimorados

A lista de aplicativos aprimorados está abaixo:

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [ELearning de cérebros maiores](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* [Lente](https://teams.microsoft.com/l/app/cfaeb687-adc7-4e36-a847-39bb35bfb631?source=app-details-dialog)
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Meus Adesivos](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [Ferramentas PDF](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Smart Connect para Jira](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [Agendamento em breve](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [Agilizar](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [TNA2 assistente de transcrição](https://teams.microsoft.com/l/app/32c31ccd-b878-470e-9259-98c079ae5528?source=app-details-dialog)
* [Umbiko](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [Waldo](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

## <a name="related-articles"></a>Artigos relacionados

* [Aplicativos do Microsoft Teams projetados para Microsoft 365 em versão prévia para o Outlook e Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Entender as funções de administrador no Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Sobre suplementos do Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Como os desenvolvedores estendem os aplicativos do Teams para trabalhar no Microsoft 365](/microsoftteams/platform/m365-apps/overview)
