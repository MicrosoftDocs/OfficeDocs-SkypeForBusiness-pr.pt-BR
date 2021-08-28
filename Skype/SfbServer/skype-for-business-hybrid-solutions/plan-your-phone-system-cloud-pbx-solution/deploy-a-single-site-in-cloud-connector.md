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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Saiba mais sobre como implantar um único site PSTN no Cloud Connector Edition.
ms.openlocfilehash: 07262f88f85602b6213dc287babbd05ddec25ed9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610538"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Implantar um único site no Cloud Connector
 
> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Saiba mais sobre como implantar um único site PSTN no Cloud Connector Edition.
  
Você pode implantar Skype for Business Cloud Connector Edition com ou sem suporte a ALTA Disponibilidade (HA). Se você quiser habilitar a HA, precisará implantar dois ou mais dispositivos em um site. Você também pode converter um dispositivo existente para dar suporte a HA depois que ele for implantado.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implantar o primeiro Skype for Business Cloud Connector Edition dispositivo

Para implantar o primeiro dispositivo em um site, abra um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo:
  
```powershell
Register-CcAppliance
```

Siga as instruções para fornecer o nome e a senha da conta de administrador do locatário. Use a conta que você criou para o gerenciamento online do Cloud Connector. Além disso, siga as instruções para fornecer a senha de certificado externo, senha de administrador de modo seguro, senha de administrador de domínio e senha de administrador de VM. 
  
Na versão 1.4.2 e anterior, siga também as instruções para fornecer a senha de certificado externo, senha de administrador de modo seguro, senha de administrador de domínio e senha de administrador de VM. 
  
Na versão 2.0 e posterior, siga também as instruções para fornecer a senha de certificado externo, a senha do CceService e a senha caBackupFile.
  
Para iniciar a instalação, abra um console do PowerShell como administrador e execute o seguinte cmdlet:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Adicionar um dispositivo a um site existente

Você pode estender um site do Cloud Connector existente para dar suporte a HA adicionando dispositivos adicionais ao site. 
  
1. Siga as etapas para preparar seu dispositivo do Cloud Connector conforme descrito em [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md). Observe que algumas etapas são necessárias apenas para o primeiro dispositivo em sua implantação. Confirme se o diretório do site existe e está configurado corretamente para suporte a HA.
    
2. Execute o cmdlet a seguir apenas no servidor host recém-adicionado para atualizar informações de topologia em sua configuração Microsoft 365 ou Office 365 organização. Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um por um:
    
   ```powershell
   Register-CcAppliance
   ```

3. Atualize a topologia em dispositivos existentes executando o seguinte cmdlet em cada servidor host. Execute apenas o cmdlet nos dispositivos existentes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Execute o cmdlet a seguir somente em servidores host recém-adicionados. Não execute este cmdlet no dispositivo existente. Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um por um.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se o diretório do site foi definido como um caminho de pasta local, você precisará definir um compartilhamento de arquivos para essa pasta e usar um caminho UNC para o diretório do site no novo dispositivo. Você pode deixar o primeiro diretório de site do dispositivo com o caminho local ou modificá-lo para usar o caminho UNC para o compartilhamento na mesma pasta. Se o local do diretório de site compartilhado mudar, todos os dispositivos instalados anteriormente precisarão ser desinstalados e reinstalados. > Importante: a senha da conta CceService e da conta CABackupFile deve ser a mesma em todos os dispositivos implantados no site, para que os dispositivos possam acessar o compartilhamento de diretório do site e o arquivo de backup de CA criptografado no diretório do site. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Remover um dispositivo de um site existente

Se você quiser remover um dispositivo de um site existente:
  
1. Execute o cmdlet a seguir somente nos servidores host que você deseja remover do site para atualizar as informações de topologia em sua configuração Microsoft 365 ou Office 365 organização.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Execute o cmdlet a seguir somente nos servidores host dos quais você deseja remover todas as máquinas virtuais do dispositivo.
    
   ```powershell
   Uninstall-CcAppliance
   ```