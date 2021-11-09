---
title: Atribua um certificado de autenticação de servidor para servidor Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumo: Atribua um certificado de autenticação de servidor para servidor para Skype for Business Server.'
ms.openlocfilehash: 30d62351d92a53c107e858ce1e0f88239f615208
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839943"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Atribua um certificado de autenticação de servidor para servidor Skype for Business Server
**Resumo:** Atribua um certificado de autenticação de servidor para servidor para Skype for Business Server.
  
Para determinar se um certificado de autenticação de servidor para servidor já foi atribuído ao Skype for Business Server, execute o seguinte comando do Shell de Gerenciamento Skype for Business Server:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Se nenhuma informação de certificado é retornada, você deve atribuir um certificado emissor de token antes de poder usar a autenticação servidor para servidor. Como regra geral, qualquer certificado Skype for Business Server pode ser usado como seu certificado OAuthTokenIssuer; por exemplo, seu Skype for Business Server certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. (O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo Assunto.) Os dois principais requisitos para o certificado usado para autenticação de servidor para servidor são estes: 1)o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus Servidores Front-End; e, 2) o certificado deve ter pelo menos 2048 bits.
  
Se você não possui um certificado que pode ser usado para autenticação servidor para servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor para servidor. Após ter solicitado e obtido o novo certificado, é possível fazer o login para qualquer um de seus Servidores de Front-End e usar um comando do Windows PowerShell semelhante a este para importar e atribuir este certificado:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado. Esse procedimento deve ser executado apenas uma vez: o serviço Skype for Business Server de replicação criará automaticamente um conjunto de tarefas agendadas que descriptografarão e implantarão o certificado em todos os servidores front-end.
  
Em alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor para servidor. (Conforme observado, o certificado padrão pode ser usado como o certificado de autenticação servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade Thumbprint do certificado padrão, use este valor para tornar o certificado padrão o certificado de autenticação servidor para servidor:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação servidor para servidor global; isto significa que o certificado será replicado e usado por todos os seus Servidores de Front-End. Novamente, este comando deve ser executado apenas uma vez e apenas em um de seus Servidores de Front-End. Embora todos os Servidores de Front-End devam usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada Servidor de Front-End. Em vez disso, configure o certificado uma vez e deixe que o Skype for Business Server de replicação tome conta de copiar esse certificado para cada servidor.
  
O Set-CsCertificate cmdlet assume o certificado em questão e configura imediatamente esse certificado para atuar como o certificado OAuthTokenIssuer atual. (Skype for Business Server mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado comece imediatamente a agir como o certificado OAuthTokenIssuer, use o cmdlet Set-CsCertificate.
  
Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado. "Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo. Por exemplo, este comando recupera o certificado padrão e configura esse certificado para assumir como o certificado OAuthTokenIssuer atual a partir de 1º de julho de 2015:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Em 1º de julho de 2015, o novo certificado será configurado como o certificado OAuthTokenIssuer atual e o certificado OAuthTokenIssuer "antigo" será configurado como o certificado anterior.
  
Se você não deseja usar o Windows PowerShell, é possível também usar o console MMC de Certificados para exportar um certificado de um Servidor de Front-End e importar este mesmo certificado em todos os seus outros Servidores de Front-End. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.
  
> [!CAUTION]
> Neste caso, o procedimento deve ser realizado em cada Servidor de Front-End. Ao exportar e importar certificados dessa maneira, Skype for Business Server não replicará esse certificado para cada Servidor Front-End. 
  
Depois que o certificado tiver sido importado para todos os servidores front-end, esse certificado poderá ser atribuído usando o Assistente de Implantação Skype for Business Server em vez de Windows PowerShell. Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador onde o Assistente de Implantação foi instalado:
  
1. Clique em Iniciar, em Todos os Programas, **Skype for Business Server** e clique **Skype for Business Server Assistente de Implantação.**
    
2. No Assistente de Implantação, clique **em Instalar ou Atualizar Skype for Business Server Sistema.**
    
3. Na página Skype for Business Server, clique no botão **Executar** sob o título **Etapa 3: Solicitar, Instalar ou Atribuir Certificados**. (Observação: Se você já instalou certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)
    
4. No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.
    
5. No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.
    
6. Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor para servidor e clique em **Avançar**.
    
7. Na página Resumo da Atribuição de Certificado, clique em **Avançar**.
    
8. Na página Executando Comandos, clique em **Concluir**.
    
9. Feche o Assistente de Certificado e Assistente de Implantação.
    

