---
title: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.openlocfilehash: 09be03b0308dfcf00a39421e2e84b75fe94a9fae
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775312"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

As salas do Microsoft Teams são executadas no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebe as mesmas versões do Windows e do sistema operacional do Windows como uma área de trabalho padrão.

As atualizações do Windows podem ser gerenciadas de algumas maneiras diferentes:

## <a name="hands-off-approach"></a>Abordagem de mãos 
- As atualizações podem ser baixadas diretamente do Windows Updates automaticamente e instaladas durante as horas. Se nenhuma alteração for feita na configuração, esse será o estado padrão.
- As atualizações não que não poderão ser adiadas instalarão automaticamente o dia um de lançamento. 
- As atualizações de qualidade e drivers serão baixadas e instaladas no dia-um automaticamente. 
- Atualizações de recursos. Veja as anotações adicionais abaixo. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Atualizações do Windows para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- As atualizações são baixadas do WU ou do seu WSUS, mas com atrasos configurados após a data de lançamento original do KB. 
- Combinadas com várias políticas de ou filtradas, isso permite a criação de "toques" de implantação, em que os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados mais tarde. Isso permite o teste de confiabilidade e desempenho em um subconjunto de sistemas antes de distribuir atualizações em toda a implantação sem a sobrecarga de gerenciamento de atualizações do Windows no SCCM, por exemplo.
- As atualizações do WSUS e do Windows para empresas podem ser [configuradas ao mesmo tempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) se você quiser tanto o gerenciamento de largura de banda quanto o controle que o Windows Update for Business oferece.
- Atualizações de recursos. Veja as anotações adicionais abaixo.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update para empresas, mas com a opção adicional de direcionar os KB específicos dentro de cada "anel" ou toda a implantação. Cada atualização pode ser implantada individualmente e testada em vez de se basear apenas em um atraso. 
- Atualizações de recursos. Veja as anotações adicionais abaixo.


### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário de qualidade e atualizações não adiadas, as "atualizações de recursos" do Windows 10 (versões principais do sistema operacional) só serão instaladas depois que o Microsoft testar e validar uma determinada funcionalidade de atualizações com as salas do Microsoft Teams. Mesmo que seja liberado para o canal semestral (ou direcionado se você tiver sistemas definidos para esse canal para teste) ou até mesmo por push manualmente por meio de suas próprias tentativas ou configurações, ele não permitirá a instalação até que o bloqueio da nossa extremidade seja removido.

A sala de equipe do Microsoft Teams "desmarcada", usando a abordagem de mãos, não instalará uma atualização do Windows ou reinicializará um dispositivo automaticamente devido a uma atualização do Windows. No entanto, os sistemas podem baixar uma atualização e esperar pela próxima reinicialização para instalá-la. A menos que alguém reinicie manualmente, a instalação deve acontecer na reinicialização noturna automática. As atualizações do Windows devem ser transparentes na sala, a interface do usuário nunca deve ser interrompida pelas atualizações do Windows.

Se você optar por ingressar no domínio, use o SCCM ou o WSUS e preste atenção especial às políticas ou ações que possam resultar na instalação de uma atualização ou na força da reinicialização durante o horário comercial. Se você tiver sistemas na sua implantação reinicializando durante o uso ou alertando sobre as atualizações do Windows pela interface do usuário, convém examinar sua configuração.
