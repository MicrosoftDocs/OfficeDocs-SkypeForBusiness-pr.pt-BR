---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são fones de áudio e faxes analógicos. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos em seu Skype for Business Server ambiente. Depois de migrar para Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use Skype for Business Server Shell de Gerenciamento para primeiro recuperar todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mover esses objetos para o pool Skype for Business Server 2019.
ms.openlocfilehash: d64552a53b5cb37187a25febe5ce6171d1c64ec9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599686"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype for Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são fones de áudio e faxes analógicos. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos em seu Skype for Business Server ambiente. Depois de migrar para Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use Skype for Business Server Shell de Gerenciamento para primeiro recuperar todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mover esses objetos para o pool Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e clique em Skype for Business Server **Shell de Gerenciamento.**

2. Na linha de comando, digite:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verifique se todos os objetos de contato foram movidos para o pool Skype for Business Server 2019. Na linha de comando, digite:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verifique se todos os objetos de contato agora estão associados ao pool Skype for Business Server 2019.


