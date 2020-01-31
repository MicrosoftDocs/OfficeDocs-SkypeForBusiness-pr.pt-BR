---
title: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.openlocfilehash: be3555507b0c9a8967b444b96e8c6e4af8f35fbf
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628557"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

As salas do Microsoft Teams são executadas no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebe as mesmas versões do Windows e do sistema operacional do Windows como um computador padrão de área de trabalho.

As atualizações do Windows podem ser gerenciadas conforme discutido nas seguintes seções:

## <a name="hands-off-approach"></a>Abordagem de mãos 

- Por padrão, as atualizações são baixadas diretamente das atualizações do Windows automaticamente e instaladas durante as horas.
- Atualização do dia de instalação de atualizações não-transferível automáticas de uma versão automática.
- Atualizações e drivers de qualidade baixar e instalar o dia-um automaticamente.
- Atualizações de recursos. Veja as observações a seguir.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Atualizações do Windows para empresas (GPO ou Intune)  

- Download [de atualizações do Windows para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- As atualizações são baixadas do Windows Update ou do seu WSUS, mas com atrasos configurados após a data de lançamento original.
- Você pode usar várias UOs ou políticas filtradas para criar "toques" de implantação, em que os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais são instalados mais tarde. A confiabilidade e o desempenho podem ser testados em um subconjunto de sistemas antes de distribuir atualizações em toda a implantação sem a sobrecarga de gerenciamento de atualizações do Windows no Configuration Manager.
- As atualizações do WSUS e do Windows para empresas podem ser [configuradas ao mesmo tempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) se você quiser tanto o gerenciamento de largura de banda quanto o controle de atualizações do Windows para empresas fornece.
- Atualizações de recursos. Veja as observações a seguir.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- Download do [WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update para empresas, mas com a opção adicional de direcionar os KB específicos dentro de cada "anel" ou toda a implantação. Cada atualização pode ser implantada individualmente e testada em vez de se basear apenas em um atraso.
- Atualizações de recursos. Veja as observações a seguir.

### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de qualidade e não-transferível, as "atualizações de recursos" do Windows 10 (versões do sistema operacional principal) só serão instaladas depois que o Microsoft testar e validar uma determinada funcionalidade de atualizações com as salas do Microsoft Teams. Mesmo que a atualização seja liberada para o canal semestral (ou direcionado se você tiver sistemas definidos para esse canal para teste) ou por push manual, um dispositivo de sistemas de sala da Microsoft não permitirá que a atualização não testada seja instalada.

As salas do Microsoft Teams funcionarão "não incluído" com uma abordagem de mãos e não instalarão uma atualização do Windows nem reinicializarão um dispositivo automaticamente para uma atualização do Windows. Os sistemas baixarão uma atualização e aguardarão a próxima reinicialização para instalá-la. A menos que alguém reinicie manualmente, a instalação ocorre apenas na reinicialização noturna automática. As atualizações do Windows devem ser transparentes na sala, e a operação normal nunca deve ser interrompida pelas atualizações do Windows.

Se você optar por usar dispositivos de ingresso no domínio, use o Gerenciador de configuração do Microsoft Endpoint ou o WSUS. Preste atenção especial às políticas ou ações que resultem em uma atualização de dispositivo ou reinício forçado durante o horário comercial. Os sistemas em sua implantação não devem ser reiniciados durante o uso ou alerta sobre atualizações do Windows pela interface do usuário durante horas de uso, confira a configuração se esse comportamento acontecer.