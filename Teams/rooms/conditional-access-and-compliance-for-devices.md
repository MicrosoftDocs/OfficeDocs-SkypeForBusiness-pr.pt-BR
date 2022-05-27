---
title: Práticas recomendadas de acesso condicional e conformidade para Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Saiba mais sobre as práticas recomendadas de acesso condicional e Intune conformidade do dispositivo e as práticas recomendadas para Salas do Microsoft Teams.
ms.openlocfilehash: b4e1d3cb91ff68e664d590c8e180e55211ca93b0
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675483"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Acesso condicional e conformidade Intune para Salas do Microsoft Teams

Este artigo fornece requisitos e práticas recomendadas para acesso condicional e políticas Intune de conformidade do dispositivo para Salas do Microsoft Teams que são usadas em espaços compartilhados.

## <a name="requirements"></a>Requisitos

Salas do Teams já deve ser implantado nos dispositivos aos quais você deseja atribuir políticas de Acesso Condicional. Se você ainda não implantou Salas do Teams, consulte Criar contas de recursos [](with-office-365.md) para salas e dispositivos Teams compartilhados e Implantar Salas do Microsoft Teams [no Android](../devices/collab-bar-deploy.md) para obter mais informações.

Um Azure Active Directory de Serviço P1 é necessário para usar o Acesso Condicional. Está incluído na licença Salas do Microsoft Teams cliente.

## <a name="teams-rooms-conditional-access-best-practices"></a>Salas do Teams práticas recomendadas de Acesso Condicional

As políticas de Acesso Condicional podem proteger o processo de entrada em dispositivos que estão em espaços compartilhados e usados por várias pessoas. Para obter uma visão geral do acesso condicional Azure Active Directory (Azure AD), consulte O que é o acesso condicional [no Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Ao usar o Acesso Condicional para proteger Salas do Teams, considere as seguintes práticas recomendadas:

-   Para simplificar a implantação e o gerenciamento, inclua todas as Microsoft 365 de recursos de sala associadas Salas do Teams em um grupo de usuários.

-   Ter um padrão de nomenclatura para todas as Salas do Teams de recursos. Por exemplo, os nomes de conta 'mtr-room1@contoso.com' e 'mtr-room2@contoso.com' começam com o prefixo 'mtr-'.
    Quando os nomes de conta são padronizados, você pode usar grupos dinâmicos no Azure AD para aplicar automaticamente políticas de Acesso Condicional a todas essas contas de uma só vez. Consulte [Regras para associação de grupos preenchidos dinamicamente](/azure/active-directory/enterprise-users/groups-dynamic-membership) para obter mais informações sobre grupos dinâmicos.

Para obter uma lista de atribuições de acesso condicional com suporte para Salas do Teams, consulte [políticas de acesso condicional com suporte](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Exemplo de política de acesso condicional

No exemplo abaixo, a política de Acesso Condicional funciona da seguinte maneira:

1.  A conta que está entrando deve ser membro de um grupo de usuários específico, neste exemplo, o grupo "Dispositivos compartilhados".

2.  A conta que está entrando só deve estar tentando acessar Exchange Online, Microsoft Teams ou SharePoint Online. As tentativas de entrar em qualquer outro aplicativo cliente serão rejeitadas.

3.  A conta de recurso deve estar entrando na plataforma Windows dispositivo.

4.  A conta de recurso também deve entrar de um local conhecido e confiável.

Se essas condições forem atendidas com êxito e o usuário inserir o nome de usuário e a senha corretos, a conta de recurso entrará no Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Acesso condicional com conformidade Microsoft Intune para Salas do Teams

Os requisitos de conformidade são regras definidas que os dispositivos devem atender para serem marcados como compatíveis, como a versão mínima do sistema operacional. Os dispositivos devem ser considerados compatíveis antes que possam ser usados para entrar em uma conta de recurso.

Para obter uma lista de políticas de conformidade Intune suporte para Salas do Teams, consulte [políticas de conformidade de dispositivo com suporte](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Para obter mais informações sobre como configurar Intune com Teams Android, consulte Configurar Intune para registrar Teams Android [baseados em Teams Android.](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Exemplo (Windows somente): Acesso condicional com Intune do dispositivo

Neste exemplo, para Salas do Teams no Windows

1. Exigir que um firewall esteja em execução Salas do Teams no Windows.

2. Exigir que o Microsoft Defender esteja em execução Salas do Teams.

3. Se uma Teams não atender a nenhum desses requisitos, ela não será marcada como compatível e os dispositivos não entrarão.

Essa política de conformidade se aplica a todos os usuários, não apenas Teams de recursos.
