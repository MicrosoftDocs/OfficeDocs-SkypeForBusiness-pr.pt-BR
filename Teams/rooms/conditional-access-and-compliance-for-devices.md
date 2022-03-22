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
description: Saiba mais sobre as políticas recomendadas de conformidade de dispositivos e acesso condicional e do Intune para Salas do Microsoft Teams.
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689049"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Conformidade condicional do Access e do Intune para Salas do Microsoft Teams

Este artigo fornece requisitos e práticas recomendadas para políticas de conformidade de dispositivos do Access e do Intune para Salas do Microsoft Teams usadas em espaços compartilhados.

## <a name="requirements"></a>Requisitos

Salas do Teams já deve ser implantado nos dispositivos aos que você deseja atribuir políticas de Acesso Condicional. Se você ainda não tiver implantado Salas do Teams, consulte [Criar](with-office-365.md) contas de recursos para salas e dispositivos Teams compartilhados e [Implantar Salas do Microsoft Teams no Android](../devices/collab-bar-deploy.md) para obter mais informações.

Um Azure Active Directory P1 Service Plan é necessário para usar o Acesso Condicional. Ele está incluído na Salas do Microsoft Teams de usuário.

## <a name="teams-rooms-conditional-access-best-practices"></a>Salas do Teams práticas recomendadas de Acesso Condicional

As políticas de Acesso Condicional podem proteger o processo de entrada em dispositivos que estão em espaços compartilhados e usados por várias pessoas. Para uma visão geral do Acesso Condicional no Azure Active Directory (Azure AD), consulte [O que é o Acesso Condicional no Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Ao usar o Acesso Condicional para proteger Salas do Teams, considere as seguintes práticas recomendadas:

-   Para simplificar a implantação e o gerenciamento, inclua todas as Microsoft 365 de recursos de sala associadas Salas do Teams em um grupo de usuários.

-   Tenha um padrão de nomenização para todas as Salas do Teams de recursos. Por exemplo, os nomes de conta 'mtr-room1@contoso.com' e 'mtr-room2@contoso.com' começam com o prefixo 'mtr-'.
    Quando os nomes de conta são padronizados, você pode usar grupos dinâmicos no Azure AD para aplicar automaticamente políticas de Acesso Condicional a todas essas contas de uma só vez. Consulte [Regras para associação de grupos preenchidos dinamicamente](/azure/active-directory/enterprise-users/groups-dynamic-membership) para obter mais informações sobre grupos dinâmicos.

Para uma lista de atribuições de Acesso Condicional com suporte para Salas do Teams, consulte [Políticas de Acesso Condicional Com Suporte](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Política de Acesso Condicional de Exemplo

No exemplo abaixo, a política de Acesso Condicional funciona da seguinte forma:

1.  A conta de entrada deve ser membro de um grupo de usuários específico, neste exemplo, o grupo "Dispositivos compartilhados".

2.  A entrada da conta deve estar apenas tentando acessar Exchange Online, Microsoft Teams ou SharePoint Online. As tentativas de entrar em qualquer outro aplicativo cliente serão rejeitadas.

3.  A conta de recurso deve estar conectado na plataforma Windows dispositivo.

4.  A conta de recurso também deve entrar de um local conhecido e confiável.

Se essas condições são atendidas com êxito e o usuário inseja o nome de usuário e a senha corretos, a conta de recurso entrará Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Acesso condicional com Microsoft Intune conformidade para Salas do Teams

Os requisitos de conformidade são regras definidas que os dispositivos devem atender para serem marcados como compatíveis, como a versão mínima do sistema operacional. Os dispositivos devem ser considerados compatíveis antes que possam ser usados para entrar em uma conta de recurso.

Para uma lista de políticas de conformidade do Intune com suporte para Salas do Teams, consulte [Políticas de conformidade de dispositivos com suporte](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Para obter mais informações sobre como configurar o Intune com Teams dispositivos Android, consulte [Configure Intune to enroll Teams Android.](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Exemplo (Windows somente): Acesso condicional com a conformidade do dispositivo Intune

Neste exemplo para Salas do Teams no Windows

1. Exigir que um firewall seja executado em Salas do Teams em Windows.

2. Exigir que o Microsoft Defender seja executado em Salas do Teams.

3. Se uma sala Teams não atender a nenhum desses requisitos, ela não será marcada como compatível e os dispositivos não entrarão.

Essa política de conformidade se aplica a todos os usuários, não apenas Teams de recursos.
