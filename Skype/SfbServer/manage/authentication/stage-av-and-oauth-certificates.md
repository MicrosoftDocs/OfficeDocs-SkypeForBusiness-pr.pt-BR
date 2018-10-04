---
title: Preparar certificados AV e OAuth no Skype para Business Server usando - Roll in Set-CsCertificate
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumo: Estágio AV e OAuth certificados para Skype para Business Server.'
ms.openlocfilehash: 9fd4074034e9bff6b27ed9a22143c59dc9890821
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375933"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Preparar certificados AV e OAuth no Skype para Business Server usando - Roll in Set-CsCertificate
 
**Resumo:** Estágio AV e OAuth certificados para Skype para Business Server.
  
Áudio/vídeo (A / V) comunicações são um componente chave do Skype para Business Server. Recursos, como compartilhamento e audioconferência e videoconferência aplicativo contam com os certificados atribuídos à / serviço de borda de V, especificamente A / V Authentication service.
  
> [!IMPORTANT]
> Esse novo recurso é projetado para funcionar para A / o certificado OAuthTokenIssuer e serviço de borda V. Outros tipos de certificados podem ser provisionados junto com A / serviço de borda V e OAuth o tipo de certificado, mas não serão beneficiados com o comportamento de coexistência que A / será de certificado do serviço de borda V.
  
O Skype para cmdlets do Shell de gerenciamento do Business Server PowerShell usados para gerenciar o Skype para certificados de servidor de negócios refere-se para A / V Edge serviço certificado como o tipo de certificado AudioVideoAuthentication e o certificado OAuthServer como typeOAuthTokenIssuer. Para o restante deste tópico e identificar de forma exclusiva os certificados, eles serão chamados pelo mesmo tipo de identificador, AudioVideoAuthentication andOAuthTokenIssuer.
  
O serviço de Autenticação A/V é responsável por emitir tokens que são usados por clientes e outros consumidores A/V. Os tokens são gerados de atributos no certificado e, quando o certificado expira, a perda de conexão e o requisito para participar novamente com um novo token gerado pelo novo certificado resultará. Um novo recurso do Skype para Business Server irá aliviar esse problema - a capacidade de estágio um novo certificado antes de começar a antiga aquele que ele expire e permitindo que os dois certificados continuar a funcionar por um período de tempo. Esse recurso usa a funcionalidade atualizada no Skype Set-CsCertificate para o cmdlet do Shell de gerenciamento do servidor de negócios. O parâmetro new-distribuição, com o parâmetro existente - EffectiveDate, colocará o novo certificado AudioVideoAuthentication no repositório de certificados. O certificado AudioVideoAuthentication mais antigo permanecerá para tokens emitidos serem validados. Começando a colocar o novo certificado AudioVideoAuthentication, a seguinte série de eventos ocorrerá:
  
> [!TIP]
> Usando o Skype para cmdlets do Shell de gerenciamento do Business Server para gerenciar certificados, você poderá solicitar certificados separados e distintos para cada finalidade no servidor de borda. Usando o Assistente de certificado no Skype para o Assistente de implantação do Business Server ajuda na criação de certificados, mas geralmente é do tipo **padrão** quais Casais usa de todos os certificados para o servidor de borda em um único certificado. A prática recomendada se você usar o recurso de agrupamento de certificado é desagrupar o certificado AudioVideoAuthentication de outros objetivos. É possível provisionar e dividir um certificado do tipo Padrão, mas apenas a parte do AudioVideoAuthentication do certificado combinado será beneficiada da separação. Um usuário estiver envolvido em (por exemplo) uma conversa de mensagem quando o certificado expirar instantânea precisará efetuar logout e logon novamente para fazer uso do novo certificado associado ao serviço de borda de acesso. Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência da Web usando o serviço de borda de webconferência. O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores. Crie e gerencie o certificado em um único local e o certificado está armazenado no repositório de gerenciamento Central para todos os outros servidores.
  
Detalhes adicionais são necessários para compreender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para dividir certificados antes do vencimento do certificado atual. -Roll parâmetro é importante, mas essencialmente único objetivo. Se você defini-la como um parâmetro, você está dizendo Set-CsCertificate que você irá fornecer informações sobre o certificado que será afetado definido pela - tipo (por exemplo AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado terá efetivo definido pela - EffectiveDate.
  
 **-Distribuir**:-Roll parâmetro é obrigatório e tem dependências que devem ser fornecidas junto com ele. Os parâmetros necessários para definir completamente quais certificados serão afetados e como eles serão aplicados:
  
 **-EffectiveDate**: O parâmetro - EffectiveDate define em que o novo certificado se tornarão co-active com o certificado atual. -EffectiveDate pode ser e está perto o tempo de expiração do certificado atual, ou pode ser um período de tempo maior. Um recomendados mínimo - EffectiveDate para o certificado AudioVideoAuthentication seria 8 horas, que é o tempo de vida de token de padrão de tokens de serviço de borda de AV emitidos usando o certificado AudioVideoAuthentication.
  
Ao separar certificados OAuthTokenIssuer, há requisitos diferentes para o tempo limite antes do certificado se tornar efetivo. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para este tempo limite é de 24 horas antes do tempo de vencimento do certificado atual. O tempo limite estendido para coexistência é por causa de outras funções do servidor que dependem do certificado OAuthTokenIssuer (por exemplo, Exchange Server) que possui um tempo de retenção maior para autenticação criada por certificado e materiais da chave de criptografia.
  
 **-Thumbprint**: O thumbprint é um atributo no certificado que é exclusivo para ele. -Thumbprint parâmetro é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.
  
 **-Tipo**:-tipo de parâmetro pode aceitar um tipo de uso do certificado único ou uma lista separada por vírgulas dos tipos de uso do certificado. Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual o objetivo do certificado. Por exemplo, o tipo AudioVideoAuthentication é para uso pelo / serviço de borda V e o serviço de autenticação de AV. Se você decidir dividir e provisionar certificados de um tipo diferente ao mesmo tempo, considere o tempo limite efetivo mínimo necessário para os certificados. Por exemplo, você precisa separar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. Seu mínimo - EffectiveDate deve ser maior dos dois certificados, neste caso o OAuthTokenIssuer, que tem um tempo de avanço mínima de 24 horas. Se você não deseja separar o certificado AudioVideoAuthentication com um tempo limite de 24 horas, separe-o com um EffectiveDate superior aos seus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um A serviço de borda V certificado com - parâmetros Roll e - EffectiveDate /

1. Faça logon no computador local como membro do grupo Administradores.
    
2. Solicitar uma renovação ou novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente na / serviço de borda V.
    
3. Importe o novo certificado AudioVideoAuthentication para o servidor de borda e outro servidor de borda em seu pool (se você tiver implantou um pool).
    
4. Configurar o certificado importado com o cmdlet Set-CsCertificate e usar o parâmetro-Roll com o parâmetro - EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos o tempo de vida do token (por padrão, oito horas). Isso nos dá um horário que o certificado deve ser definido como ativo e é - EffectiveDate \<cadeia de caracteres\>: "7/22/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Para um pool de borda, você deve ter todos os certificados AudioVideoAuthentication implantados e configurados pela data e hora definido pelo parâmetro - EffectiveDate do certificado primeiro implantado para evitar uma possível / interrupção de comunicações V devido a antiguidade certificado expirando antes de todos os tokens de cliente e consumidor foram renovados usando o novo certificado. 
  
    O comando Set-CsCertificate com o parâmetro-Roll e - EffectiveTime:
    
   ```
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Um comando Set-CsCertificate de exemplo:
    
   ```
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder as configurações de idioma e região do seu servidor. O exemplo usa as configurações de Idioma e Região Inglês dos EUA 
  
Para compreender melhor o processo que Set-CsCertificate, - Roll e - EffectiveDate usar para preparar um novo certificado para emitindo tokens AudioVideoAuthentication novos enquanto estiver usando um certificado existente para validar AudioVideoAuthentication que estão sendo usados por consumidores, um cronograma visual é uma maneira eficaz de Noções básicas sobre o processo. O exemplo a seguir, o administrador determina que A / certificado do serviço de borda V está prestes a expirar em 2:00:00 PM em 07/22/2015. Ele solicita e recebe um novo certificado e importa-lo para cada servidor de borda em seu pool. Às 2h da manhã em 07/22/2015, ele começa a executar Get-CsCertificate com - Roll, - impressão digital igual a cadeia de caracteres de impressão digital do novo certificado e - EffectiveTime definida como 22/07/2015 6:00:00 AM. Ele executa este comando em cada servidor de borda.
  
![Usando os parâmetros Roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Legenda**|**Estágio**|
|:-----|:-----|
|1  <br/> |Início: 22/07/2015 00:00:00  <br/> O certificado AudioVideoAuthentication atual expira 14:00:00 em 22/07/2015. Isso é determinado pelo carimbo de data/hora de vencimento no certificado. Planeje a substituição e sobreposição do certificado na conta para sobreposição de 8 horas (tempo do token padrão) antes do certificado existente atingir a hora de vencimento. O tempo limite 02:00:00 é utilizado neste exemplo para permitir que o administrador tenha tempo suficiente para colocar e provisionar os novos certificados antes da hora efetiva 06:00:00.  <br/> |
|2  <br/> |22/07/2015 02:00:00 - 22/07/2015 05:59:59  <br/> Definir os certificados nos servidores de borda com tempo efetivo de 6:00:00 AM (4 horas prazo é neste exemplo, mas pode ser mais tempo) usando Set-CsCertificate-tipo \<tipo de uso de certificados\> -Thumbprint \<impressão digital do novo certificado\> - Distribuir - EffectiveDate \<cadeia de caracteres de data/hora do tempo efetivo para o novo certificado\>  <br/> |
|3  <br/> |22/07/2015 06:00 - 22/07/2015 14:00  <br/> Para validar tokens, o novo certificado é usado primeiro e, se o novo certificado não conseguir validar o token, o certificado antigo será usado. Esse processo é usado para todos os tokens durante o período de sobreposição de 8 horas (tempo do token padrão).  <br/> |
|4  <br/> |Fim: 22/07/2015 14:00:01  <br/> O certificado antigo expirou e o novo certificado foi usado. Certificado antigo pode ser removido com segurança com Remove-CsCertificate-tipo \<tipo de uso de certificados\> -anterior  <br/> |
   
Quando a hora efetiva é atingida (22/07/2015 06:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo é testado. O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo. Quando o certificado antigo vencer (22/07/2015 14:00:00 PM), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o - parâmetro anterior.

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um OAuthTokenIssuer certificado com - parâmetros Roll e - EffectiveDate

1. Faça logon no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no servidor Front-End.
    
3. Importe o novo certificado OAuthTokenIssuer para um servidor Front-End em seu pool (se você tiver implantou um pool). O certificado OAuthTokenIssuer é replicado globalmente e apenas precisa ser atualizado ou renovado em qualquer servidor da sua implantação. Servidor Front-End é usado como um exemplo.
    
4. Configurar o certificado importado com o cmdlet Set-CsCertificate e usar o parâmetro-Roll com o parâmetro - EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos um mínimo de 24 horas. 
    
    O comando Set-CsCertificate com o parâmetro-Roll e - EffectiveTime:
    
   ```
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Um comando Set-CsCertificate de exemplo:
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> O EffectiveDate deve ser formatado para corresponder as configurações de idioma e região do seu servidor. O exemplo usa as configurações de Idioma e Região Inglês dos EUA 
  
Quando a hora efetiva é atingida (21/07/2015 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo é testado. O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo. Quando o certificado antigo vencer (22/07/2015 14:00:00 PM), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o - parâmetro anterior.
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Consulte também

[Gerenciar a autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)