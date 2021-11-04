---
title: Certificados AV e OAuth de estágio em Skype for Business Server usando -Roll no Set-CsCertificate
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumo: Estágio AV e certificados OAuth para Skype for Business Server.'
ms.openlocfilehash: 0d5a5a68ac63b514967b33692abfeb15d8459995
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767849"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Certificados AV e OAuth de estágio em Skype for Business Server usando -Roll no Set-CsCertificate
 
**Resumo:** Estágio AV e certificados OAuth para Skype for Business Server.
  
As comunicações de áudio/vídeo (A/V) são um componente-chave do Skype for Business Server. Recursos como compartilhamento de aplicativos e conferência de áudio e vídeo dependem dos certificados atribuídos ao serviço de Borda A/V, especificamente o serviço de Autenticação A/V.
  
> [!IMPORTANT]
> Esse novo recurso foi projetado para funcionar para o serviço de Borda A/V e para o certificado OAuthTokenIssuer. Outros tipos de certificado podem ser provisionados juntamente com o serviço de Borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de Borda A/V irá.
  
Os cmdlets do Shell de Gerenciamento do PowerShell do Skype for Business Server usados para gerenciar certificados Skype for Business Server referem-se ao certificado de serviço de Borda A/V como o tipo de certificado AudioVideoAuthentication e o certificado OAuthServer como typeOAuthTokenIssuer. Para o restante deste tópico e identificar exclusivamente os certificados, eles serão referenciados pelo mesmo tipo de identificador, AudioVideoAuthentication eOAuthTokenIssuer.
  
O serviço de Autenticação A/V é responsável pela emissão de tokens que são usados por clientes e outros consumidores A/V. Os tokens são gerados a partir de atributos no certificado e, quando o certificado expirar, a perda de conexão e a necessidade de se reunir com um novo token gerado pelo novo certificado resultarão. Um novo recurso no Skype for Business Server aliviará esse problema - a capacidade de estágio de um novo certificado antes do antigo expirar e permitir que ambos os certificados continuem a funcionar por um período de tempo. Esse recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate Skype for Business Server Shell de Gerenciamento. O novo parâmetro -Roll, com o parâmetro existente -EffectiveDate, colocará o novo certificado AudioVideoAuthentication no armazenamento de certificados. O certificado AudioVideoAuthentication mais antigo ainda permanecerá para tokens emitidos a serem validados. A partir da colocação do novo certificado AudioVideoAuthentication, ocorrerá a seguinte série de eventos:
  
> [!TIP]
> Usando os cmdlets Skype for Business Server Shell de Gerenciamento para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no Servidor de Borda. Usar o Assistente de Certificado no Assistente de Implantação Skype for Business Server ajuda você na  criação de certificados, mas normalmente é do tipo padrão que casa todos os certificados usa para o Servidor de Borda em um único certificado. A prática recomendada se você for usar o recurso de certificado de rolagem é desacompilar o certificado AudioVideoAuthentication de outras finalidades de certificado. Você pode provisionar e estágio de um certificado do tipo Padrão, mas somente a parte AudioVideoAuthentication do certificado combinado se beneficiará da preparação. Um usuário envolvido em (por exemplo) uma conversa de mensagens instantâneas quando o certificado expirar precisará fazer logoff e fazer logoff novamente para fazer uso do novo certificado associado ao serviço de Borda de Acesso. Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência da Web usando o serviço de Borda de WebConferência. O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores. Você cria e gerencia o certificado em um só lugar e o certificado é armazenado no armazenamento de Gerenciamento Central para todos os outros servidores.
  
Detalhes adicionais são necessários para entender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para estágios de certificados antes da expiração do certificado atual. O parâmetro -Roll é importante, mas essencialmente único. Se você defini-lo como um parâmetro, você estará informando Set-CsCertificate que fornecerá informações sobre o certificado que será afetado definido por -Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornará efetivo definido por -EffectiveDate.
  
 **-Roll**: o parâmetro -Roll é necessário e tem dependências que devem ser fornecidas junto com ele. Os parâmetros necessários para definir totalmente quais certificados serão afetados e como serão aplicados:
  
 **-EffectiveDate**: o parâmetro -EffectiveDate define quando o novo certificado se tornará co-ativo com o certificado atual. O -EffectiveDate pode estar próximo do tempo de expiração do certificado atual, ou pode ser um período mais longo de tempo. Um mínimo recomendado -EffectiveDate para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo de vida do token padrão para tokens de serviço de Borda AV emitidos usando o certificado AudioVideoAuthentication.
  
Ao fazer a preparação de certificados OAuthTokenIssuer, há requisitos diferentes para o tempo de entrega antes que o certificado possa ser efetivado. O tempo mínimo que o certificado OAuthTokenIssuer deve ter pelo seu tempo de entrega é de 24 horas antes do tempo de expiração do certificado atual. O tempo de vantagem estendido para a coexistência é devido a outras funções de servidor que dependem do certificado OAuthTokenIssuer (Exchange Server, por exemplo) que tem um tempo de retenção maior para os materiais chave de autenticação e criptografia criados pelo certificado.
  
 **-Thumbprint**: A impressão digital é um atributo no certificado exclusivo desse certificado. O parâmetro -Thumbprint é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.
  
 **-Type**: O parâmetro -Type pode aceitar um único tipo de uso de certificado ou uma lista separada por vírgulas dos tipos de uso do certificado. Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual é a finalidade do certificado. Por exemplo, digite AudioVideoAuthentication para uso pelo serviço de Borda A/V e pelo serviço de Autenticação AV. Se você decidir em estágio e provisionar certificados de um tipo diferente ao mesmo tempo, considere o tempo de entrega mínimo mínimo necessário para os certificados. Por exemplo, você precisa estágio de certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. Seu mínimo -EffectiveDate deve ser o maior dos dois certificados, nesse caso, o OAuthTokenIssuer, que tem um tempo de entrega mínimo de 24 horas. Se você não quiser estágio do certificado AudioVideoAuthentication com um tempo de vantagem de 24 horas, estabelecia-o separadamente com um EffectiveDate que está mais para seus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado de serviço de Borda A/V com parâmetros -Roll e -EffectiveDate

1. Faça logoff no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou um novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente no serviço de Borda A/V.
    
3. Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).
    
4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro -Roll com o parâmetro -EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 14:00:00) menos tempo de vida útil do token (por padrão, oito horas). Isso nos dá uma hora em que o certificado deve ser definido como ativo e é -EffectiveDate \<string\> : "22/07/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Para um pool de Borda, você deve ter todos os certificados AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro -EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções de comunicações A/V devido ao certificado mais antigo expirar antes que todos os tokens de cliente e consumidor tenham sido renovados usando o novo certificado. 
  
    O Set-CsCertificate com o parâmetro -Roll e -EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Um exemplo Set-CsCertificate comando:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do servidor. O exemplo usa as configurações região e idioma inglês dos EUA 
  
Para entender ainda mais o processo que Set-CsCertificate, -Roll e -EffectiveDate usam para configurar um novo certificado para a emissão de novos tokens AudioVideoAuthentication enquanto ainda usa um certificado existente para validar AudioVideoAuthentication que estão em uso pelos consumidores, uma linha do tempo visual é um meio eficaz de entender o processo. No exemplo a seguir, o administrador determina que o certificado de serviço de Borda A/V deve expirar às 14:00:00 em 22/07/2015. Ele solicita e recebe um novo certificado e o importa para cada Servidor de Borda em seu pool. Às 2 da manhã do dia 22/07/2015, ele começa a executar o Get-CsCertificate com -Roll, -Thumbprint igual à cadeia de caracteres de impressão digital do novo certificado e -EffectiveTime definido como 22/07/2015 6:00:00 AM. Ele executa esse comando em cada Servidor de Borda.
  
![Usando os parâmetros Roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Etapa**|
|:-----|:-----|
|1  <br/> |Início: 22/07/2015 12:00:00  <br/> O certificado audiovideoAuthentication atual deve expirar às 14:00:00 em 22/07/2015. Isso é determinado pelo carimbo de data/hora expira no certificado. Planeje a substituição e a substituição do certificado para levar em conta uma sobreposição de 8 horas (tempo de vida do token padrão) antes que o certificado existente atinja o tempo de expiração. O tempo de avanço das 2:00:00 é usado neste exemplo para permitir que o administrador coloque e provisione os novos certificados com antecedência do horário efetivo das 6:00:00.  <br/> |
|2  <br/> |22/07/2015 2:00:00 - 22/07/2015 05:59:59  <br/> Definir Certificados em Servidores de Borda com tempo efetivo de 6:00:00 (o tempo de vantagem de 4 horas é para este exemplo, mas pode ser maior) usando o Set-CsCertificate \<certificate usage type\> -Type -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3  <br/> |22/07/2015 06:00 - 22/07/2015 14:00  <br/> Para validar tokens, o novo certificado será experimentado primeiro e, se o novo certificado não validar o token, o certificado antigo será tentado. Esse processo é usado para todos os tokens durante o período de sobreposição de 8 horas (tempo de vida do token padrão).  <br/> |
|4  <br/> |Fim: 22/07/2015 14:00:01  <br/> O certificado antigo expirou e o novo certificado foi assumido. O certificado antigo pode ser removido com segurança com Remove-CsCertificate -Type \<certificate usage type\> -Previous  <br/> |
   
Quando a hora efetiva é atingida (22/07/2015 6:00:00), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado. Se a validação falhar, o certificado antigo será tentado. O processo de tentar o novo e voltar ao certificado antigo continuará até o tempo de expiração do certificado antigo. Depois que o certificado antigo expirar (22/07/2015 14:00), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado OAuthTokenIssuer com parâmetros -Roll e -EffectiveDate

1. Faça logoff no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou um novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no Servidor front-end.
    
3. Importe o novo certificado OAuthTokenIssuer para um Servidor Front-End em seu pool (se você tiver um pool implantado). O certificado OAuthTokenIssuer é replicado globalmente e só precisa ser atualizado e renovado em qualquer servidor em sua implantação. O Servidor Front-End é usado como exemplo.
    
4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro -Roll com o parâmetro -EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 14:00 pm) menos um mínimo de 24 horas. 
    
    O Set-CsCertificate com o parâmetro -Roll e -EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Um exemplo Set-CsCertificate comando:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do servidor. O exemplo usa as configurações região e idioma inglês dos EUA 
  
Quando a hora efetiva é atingida (21/07/2015 1:00:00), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado. Se a validação falhar, o certificado antigo será tentado. O processo de tentar o novo e voltar ao certificado antigo continuará até o tempo de expiração do certificado antigo. Depois que o certificado antigo expirar (22/07/2015 14:00), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro -Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos parceiros no Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)