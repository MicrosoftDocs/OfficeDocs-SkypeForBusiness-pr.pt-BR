---
title: Gerenciar Windows atualizações para Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: O administrador pode aprender sobre como gerenciar Windows atualizações e Windows de recursos para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67144ff29077a3dec6be79b9b68efb1162d31a9069b3436b29f9ac50a4857914
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275957"
---
# <a name="manage-windows-updates"></a>Gerenciar Windows atualizações

Salas do Microsoft Teams é executado em Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas Windows atualizações e builds do sistema operacional como um computador de área de trabalho padrão.

Windows As atualizações podem ser gerenciadas conforme discutido nas seguintes seções:

## <a name="hands-off-approach"></a>Abordagem prática 

- Por padrão, as atualizações são baixadas diretamente Windows atualizações automaticamente e instaladas durante o horário de folga.
- Atualizações não adiáveis instalam o primeiro dia da versão automaticamente.
- Atualizações de qualidade e drivers baixam e instalam o primeiro dia automaticamente.
- Atualizações de recursos. Consulte as anotações a seguir.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Atualizações para Empresas (GPO ou Intune)  

- [Windows download de Atualizações para Empresas](/windows/deployment/update/waas-manage-updates-wufb)
- As atualizações são baixadas do Windows Update ou do WSUS, mas com atrasos configurados após a data de lançamento original.
- Você pode usar várias OUs ou políticas filtradas para criar "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados posteriormente. A confiabilidade e o desempenho podem ser testados em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar Windows atualizações no Configuration Manager.
- O WSUS e Windows atualizações para [](/windows/deployment/update/waas-integrate-wufb) Empresas podem ser configuradas ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle Windows Atualizações para Empresas fornece.
- Atualizações de recursos. Consulte as anotações a seguir.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Download do WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Assim como Windows Atualizar para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação. Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.
- Atualizações de recursos. Consulte as anotações a seguir.

### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de Qualidade e Não Adiáveis, Windows 10 "Atualizações de Recursos" (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com Salas do Microsoft Teams. Mesmo que a atualização seja lançada no Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou manualmente pressionado, um dispositivo microsoft room Systems não permitirá que a atualização não testada seja instalada.

Salas do Microsoft Teams funciona "fora da caixa" com uma abordagem prática e não instalará um Windows Update ou reiniciará um dispositivo automaticamente para uma atualização Windows. Os sistemas baixam uma atualização e aguardam a próxima reinicialização para instalá-la. A menos que alguém o reinicia manualmente, a instalação só acontece na reinicialização automática noturna. Windows As atualizações devem ser transparentes na sala e a operação normal nunca deve ser interrompida por Windows Atualizações.

Se você optar por ingressar em dispositivos de domínio, use Microsoft Endpoint Configuration Manager ou WSUS. Preste atenção especial a políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial. Os sistemas em sua implantação não devem ser reiniciados durante o uso ou alerta sobre Windows atualizações na interface do usuário durante o horário de uso, revise sua configuração se esse comportamento acontecer.