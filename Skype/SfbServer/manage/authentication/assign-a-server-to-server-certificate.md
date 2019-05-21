---
title: Atribuir um certificado de autenticação de servidor a servidor ao Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumo: atribuir um certificado de autenticação de servidor a servidor para o Skype for Business Server.'
ms.openlocfilehash: 7198c103a771029ec93e589169fafb652f5d8842
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278346"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Atribuir um certificado de autenticação de servidor a servidor ao Skype for Business Server
**Resumo:** Atribuir um certificado de autenticação de servidor a servidor para o Skype for Business Server.
  
Para determinar se um certificado de autenticação de servidor para servidor já foi atribuído ao Skype for Business Server, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server:
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Se nenhuma informação de certificado for retornada, você deverá atribuir um certificado emissor de token antes de poder usar a autenticação servidor- servidor. Como regra geral, qualquer certificado do Skype for Business Server pode ser usado como seu certificado do OAuthTokenIssuer; por exemplo, seu certificado padrão do Skype for Business Server também pode ser usado como o certificado OAuthTokenIssuer. (O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo assunto.) Os dois requisitos principais para o certificado usado para a autenticação de servidor para servidor são estes: 1) o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus servidores front-end; e 2) o certificado deve ter pelo menos 2048 bits.
  
Se você não tiverum certificado que possa ser usado para autenticação servidor-servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor-servidor. Depois de solicitar e obter o novo certificado, você pode fazer logon em qualquer um dos seus servidores front-end e usar um comando do Windows PowerShell semelhante a este para importar e atribuir esse certificado:
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado. Este procedimento deve ser executado apenas uma vez: o serviço de replicação do Skype for Business Server criará automaticamente um conjunto de tarefas agendadas que descriptografarão e implantarão o certificado em todos os seus servidores front-ends.
  
Como alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor-servidor. (Conforme observado, o certificado padrão pode ser usado como certificado de autenticação de servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade de impressão digital do certificado padrão e, em seguida, usa esse valor para torná-lo o certificado padrão do certificado de autenticação de servidor para servidor:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação de servidor para servidor global; Isso significa que o certificado será replicado para e usado por todos os seus servidores front-end. Novamente, esse comando só deve ser executado uma vez e somente em um dos seus servidores front-end. Apesar de todos os servidores front-end precisarem usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada servidor front-end. Em vez disso, configure o certificado uma vez e deixe que o servidor de replicação do Skype for Business Server assuma a cópia desse certificado para cada servidor.
  
O cmdlet Set-CsCertificate leva o certificado em questão e configura imediatamente esse certificado para atuar como o certificado OAuthTokenIssuer atual. (O Skype for Business Server mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado comece imediatamente a atuar como o certificado OAuthTokenIssuer, use o cmdlet Set-CsCertificate.
  
Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado. "Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo. Por exemplo, esse comando recupera o certificado padrão e configura o certificado para assumir como o certificado OAuthTokenIssuer atual a partir de 1° de julho de 2015:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Em 1 ° de julho de 2015, o novo certificado será configurado como o atual certificado de OAuthTokenIssuer e o certificado de OAuthTokenIssuer "antigo" será configurado como o certificado anterior.
  
Se não quiser usar o Windows PowerShell, você também pode usar o console MMC de certificados para exportar um certificado de um servidor front-end e, em seguida, importar esse mesmo certificado em todos os outros servidores front-end. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.
  
> [!CAUTION]
> Nesse caso, o procedimento deve ser executado em cada servidor front-end. Ao exportar e importar certificados dessa maneira, o Skype for Business Server não replicará esse certificado para cada servidor front-end. 
  
Após a importação do certificado para todos os seus servidores front-end, esse certificado pode ser atribuído usando o assistente de implantação do Skype for Business Server, em vez do Windows PowerShell. Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador no qual o Assistente de Implantação tenha sido instalado:
  
1. Clique em Iniciar, em todos os programas, em **Skype for Business Server**e, em seguida, clique em **Assistente de implantação do Skype for Business Server**.
    
2. No assistente de implantação, clique em **instalar ou atualizar o sistema do Skype for Business Server**.
    
3. Na página do Skype for Business Server, clique no botão **executar** abaixo do título **etapa 3: solicitar, instalar ou atribuir certificados**. (Observação: Se você já tiver instalado certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)
    
4. No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.
    
5. No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.
    
6. Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor-servidor e clique em **Avançar**.
    
7. Na página Resumo da Atribuição de Certificado, clique em **Avançar**.
    
8. Na página Executando Comandos, clique em **Concluir**.
    
9. Feche o Assistente de Certificado e Assistente de Implantação.
    

