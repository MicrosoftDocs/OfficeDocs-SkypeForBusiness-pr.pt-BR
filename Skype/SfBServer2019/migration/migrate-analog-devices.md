---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Skype for Business Server oferece suporte a dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são telefones de áudio analógicos e máquinas de fax analógicas. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos no ambiente do Skype for Business Server. Depois de migrar para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use o Shell de gerenciamento do Skype for Business Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mova esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813589"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

O Skype for Business Server oferece suporte a dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são telefones de áudio analógicos e máquinas de fax analógicas. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos no ambiente do Skype for Business Server. Depois de migrar para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use o Shell de gerenciamento do Skype for Business Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mova esses objetos para o pool do Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.

2. Na linha de comando, digite:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verifique se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019. Na linha de comando, digite:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.


