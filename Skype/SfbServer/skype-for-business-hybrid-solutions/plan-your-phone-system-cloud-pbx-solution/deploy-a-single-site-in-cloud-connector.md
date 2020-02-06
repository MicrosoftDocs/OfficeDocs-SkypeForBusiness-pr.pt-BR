---
title: Implantar um único site no Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Saiba como implantar um único local de PSTN no Cloud Connector Edition.
ms.openlocfilehash: 09aa2e2a7417539757c70368e4f7a508de57bc7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799701"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
Saiba como implantar um único local de PSTN no Cloud Connector Edition.
  
Você pode implantar o Skype for Business Cloud Connector Edition com ou sem suporte de alta disponibilidade (HA). Se desejar habilitar alta disponibilidade, você precisará implantar dois ou mais dispositivos em um site. Você também pode converter um dispositivo existente para dar suporte à alta disponibilidade após a implantação.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implantar o primeiro dispositivo do Skype for Business Cloud Connector Edition

Para implantar o primeiro dispositivo em um site, abra um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo:
  
```powershell
Register-CcAppliance
```

Siga as instruções para fornecer o nome e a senha da conta de administrador de locatários. Use a conta que você criou para o gerenciamento online do Cloud Connector. Além disso, siga as instruções para fornecer a senha do certificado externo, a senha do administrador de modo de segurança, a senha do administrador do domínio e a senha do administrador da VM.  
  
Na versão 1.4.2 e versões anteriores, também siga as instruções para fornecer a senha do certificado externo, a senha de administrador do modo de segurança, a senha de administrador do domínio e a senha do administrador da VM. 
  
Na versão 2.0 e posteriores, siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.
  
Para iniciar a instalação, abra um console do PowerShell como administrador e execute o seguinte cmdlet:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Adicionar um dispositivo a um site existente

Você pode estender um site existente do conector de nuvem para dar suporte à alta disponibilidade adicionando mais aparelhos ao site. 
  
1. Siga as etapas para preparar o seu aparelho de conexão de nuvem conforme descrito em [preparar seu aparelho de conector de nuvem](prepare-your-cloud-connector-appliance.md). Note que algumas etapas são necessárias apenas para o primeiro dispositivo em sua implantação. Confirme se o diretório do site existe e se está configurado corretamente para oferecer suporte para alta disponibilidade.
    
2. Execute o cmdlet a seguir apenas no servidor host recém-adicionado para atualizar as informações de topologia na configuração do locatário do O365. Se quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um:
    
   ```powershell
   Register-CcAppliance
   ```

3. Atualize a topologia nos dispositivos existentes executando o cmdlet a seguir em cada servidor host. Execute o cmdlet apenas nos dispositivos existentes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Execute o cmdlet a seguir apenas em servidores host recém-adicionados. Não execute esse cmdlet no dispositivo existente. Se quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se o diretório de sites estiver configurado como um caminho de pasta local, você precisará definir um compartilhamento de arquivos para essa pasta e usar um caminho UNC para o diretório de sites no novo dispositivo. Você pode deixar o diretório de sites do primeiro dispositivo com o caminho local ou modificá-lo para usar o caminho UNC para o compartilhamento na mesma pasta. Se o local do diretório de sites compartilhado mudar, todos os dispositivos instalados anteriormente precisarão ser desinstalados e reinstalados. > importante: a senha da conta CceService e da conta CABackupFile devem ser iguais em todos os aparelhos implantados no site, para que os aparelhos possam acessar o compartilhamento do diretório de sites e o arquivo de backup da CA criptografada no diretório de sites. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Remover um dispositivo de um site existente

Se você deseja remover um dispositivo de um site existente:
  
1. Execute o cmdlet a seguir apenas nos servidores host que você deseja remover do site para atualizar as informações de topologia na configuração do locatário do O365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Execute o cmdlet a seguir apenas nos servidores host dos quais você deseja remover todas as máquinas virtuais do dispositivo.
    
   ```powershell
   Uninstall-CcAppliance
   ```


