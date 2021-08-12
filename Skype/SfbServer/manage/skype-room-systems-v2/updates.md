---
title: Gerenciar Windows atualizações para Salas do Microsoft Teams
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gerenciar Windows atualizações para Salas do Microsoft Teams
ms.openlocfilehash: 086e1c760fce14bc163a92021fee4e2e35694267cf4f8a8d3733f93f5e078106
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311069"
---
# <a name="manage-windows-updates"></a>Gerenciar Windows atualizações

Salas do Microsoft Teams é executado Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas Windows atualizações e builds do sistema operacional como uma área de trabalho padrão.

Windows As atualizações podem ser gerenciadas de algumas maneiras diferentes:

## <a name="hands-off-approach"></a>Abordagem prática 
- As atualizações podem ser baixadas diretamente Windows atualizações automaticamente e instaladas durante o horário de folga. Se nenhuma alteração for feita na configuração, este será o estado padrão.
- Atualizações não adiáveis instalarão o primeiro dia da versão automaticamente. 
- Atualizações de qualidade e drivers baixarão e instalarão o primeiro dia automaticamente. 
- Atualizações de Recursos. Consulte observações adicionais abaixo. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Atualizações para Empresas](/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- As atualizações são baixadas do WU ou do WSUS, mas com atrasos configurados após a data de lançamento original do KB. 
- Combinado com várias políticas de OU ou filtradas, isso permite a criação de "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados posteriormente. Isso permite testes de confiabilidade e desempenho em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar atualizações do Windows no Microsoft Endpoint Configuration Manager por exemplo.
- O WSUS e Windows atualizações para [](/windows/deployment/update/waas-integrate-wufb) Empresas podem ser configuradas ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle Windows Atualizações para Empresas fornece.
- Atualizações de recursos. Consulte observações adicionais abaixo.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido Windows Atualizar para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação. Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso. 
- Atualizações de recursos. Consulte observações adicionais abaixo.


### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de Qualidade e Não Adiáveis, Windows 10 "Atualizações de Recursos" (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com o Salas do Microsoft Teams. Mesmo que ele seja lançado para o Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou até mesmo manualmente pressionado por suas próprias tentativas ou configurações, ele não permitirá a instalação até que o bloco em nossa extremidade seja removido.

Microsoft Teams A sala "pronto para uso", usando a abordagem de hands off, não instalará um Windows Atualizar ou reiniciará um dispositivo automaticamente devido a uma atualização Windows Atualização. No entanto, os sistemas podem baixar uma atualização e aguardar a próxima reinicialização para instalá-la. A menos que alguém o reinicie manualmente, a instalação deve ocorrer na reinicialização automática noturna. Windows As atualizações devem ser transparentes na sala, a interface do usuário nunca deve ser interrompida por Windows Atualizações.

Se você optar por ingressar no domínio, use Microsoft Endpoint Configuration Manager ou WSUS e preste atenção especial a políticas ou ações que podem resultar na instalação de uma atualização ou forçando uma reinicialização durante o horário comercial. Se você tiver sistemas em sua implantação reiniciando durante o uso ou alertando sobre Windows atualizações na interface do usuário, você vai querer ver sua configuração.