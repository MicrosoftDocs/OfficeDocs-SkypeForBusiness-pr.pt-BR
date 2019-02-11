---
title: Suporte de migração Exchange Unified Messaging Online
ms.author: heidip
author: heidip
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft é retirada de Unificação de mensagens (ExchUMO) serviço do Exchange Online por de 2020 fevereiro. Este artigo resume o que afetaram os clientes devem saber e fazer para planejar seu continuidade de negócios.
ms.openlocfilehash: af9418a764780efca07a37f1c0b55415d0305f55
ms.sourcegitcommit: 3070dd7c091e6c97c6d746c6bfb866625184ba87
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "29786418"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte de migração Exchange Unified Messaging Online  

Refere-se o [comunicado](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) em 8 de fevereiro de 2019, Microsoft é retirada de Unificação de mensagens (ExchUMO) serviço do Exchange Online por de 2020 fevereiro. Este artigo oferece um resumo das quais clientes afetados deve saber e fazer para planejar seu continuidade de negócios. 
 
ExchUMO é implantado por clientes para os serviços de integração de fax, caixa postal e/ou atendedor automático. Microsoft planos ajudar a esses clientes migrar para seus serviços baseados em nuvem que suportam milhares de clientes já em Skype para Business Online e Teams da Microsoft. 

Caixa postal é basicamente uma orientado a Microsoft migração; envolvimento Admin e/ou investimento pode ser necessário para um subconjunto dos clientes. Atendedor automático é uma migração conduzido pelo administrador; Você precisará recriar as árvores de atendedor automático de ExchUMO existentes no serviço de nuvem do atendedor automático de nuvem. Os clientes que estão consumindo qualquer um dos recursos ExchUMO com um PBX de terceiros não serão migrados para os serviços de nuvem do Skype porque eles não têm suporte para sistemas de PBX de terceiros. Um plano de aposentadoria para suporte de terceiros foi anunciado no ano passado [neste](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
)blog e clientes nesse modelo de implantação podem migrar seus usuários para uma das plataformas/serviços de comunicação unificada da Microsoft ou adquirir uma caixa postal de terceiros e/ou solução de atendedor automático para estes usuários. Não há suporte para integração de fax nos serviços de nuvem; os clientes precisarão migrar para uma solução de terceiros. 

### <a name="who-is-affected"></a>Quem será afetado?

Os clientes que estão consumindo qualquer um dos seguintes recursos do serviço Exchange Unified Messaging Online são afetados:

1. Serviço de caixa postal 
2. Serviço de atendedor automático 
3. Integração de fax 

> [!Note]
> Clientes que estão usando qualquer um do Exchange Server local com a Unificação de mensagens não são afetados. 

Saiba mais sobre o usuário e o impacto de experiência de administração no [impacto de experiência do usuário](#user-experience-impact).

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e vai ser ajudando os clientes a migrar com base no seguinte plano. 


|Grupo de clientes |Linha do tempo  |Detalhes  |
|---------|---------|---------|
|Clientes que estiver prontos para migrar<br><br>Recursos de migração:<br><ul><li>Caixa postal</ul>   |   Março – maio de 2019  |Exemplos:<ul><li>    Clientes com caixa postal simples implantação e uso<li>Clientes que tenham todos os requisitos estabelecidos para a Microsoft executar a migração<ul>|
|Clientes com os pré-requisitos<br><br>Recursos de migração:<br><ul><li>Caixa postal<li>Atendedor automático</ul> |  Maio – dezembro de 2019 |Exemplos: <br><ul><li>Configuração híbrida não será estabelecida/concluída<li>Os números PSTN híbrida não são configurados</ul>|
|Clientes que requerem o investimento de cliente do admin envolvimento &<br><br>Recursos de migração:<ul><li>caixa postal<li>Atendedor automático<li>Integração de fax</ul>| Por fevereiro de 2020  | Exemplos: <br><ul><li>Serviço de ExchUMO é consumido por 3º PBX de terceiros<li>Clientes com requisitos de acesso do assinante de PSTN<li>Clientes em 2010 SFB (não é suportada)<li>Integração de fax</ul> |

## <a name="migration-steps"></a>Etapas de migração

1.  **Obter informados**
 
    Familiarize-se com o [comunicado do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e neste artigo para planejar uma migração suave para seus usuários. Consulte [Verificar Skype para caixa postal de negócios e opções](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os recursos de caixa postal de nuvem.  
 

2.  **Estabelecer um Skype para topologia híbrida de negócios**

    Se você não tiver um Skype para topologia híbrida de negócios estabelecida, você precisará fazer isso para habilitar uma migração suave dos seus usuários de caixa postal. Consulte [Configure Skype para o híbrido de negócios](../hybrid/configure-federation-with-skype-for-business-online.md) para obter mais detalhes. 

    > [!Note]
    > Você não precisará migrar seus usuários para online para a migração de serviço de correio de voz. No entanto, para usuários no local aproveitar o serviço de correio de voz baseado em nuvem, uma topologia híbrida é deve ser estabelecida.

3. **Planejar a migração de atendedor automático**
    
    Admins pode começar a migrar seus atendedores automáticos de ExchUMO para o atendedor automático da nuvem a qualquer momento. Para obter mais detalhes, consulte [Configurar um atendedor automático de sistema telefônico](../../SfbOnline/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md) . Microsoft planos fornecer recursos de atendedor automático adicionais que os clientes considerar essenciais para sua migração por de 2019 março. Os administradores devem avaliar o conjunto de recursos e migrar suas instâncias do atendedor automático de acordo. Para comparação da lista de recursos, consulte a [matriz de recurso de serviços em nuvem ExchUMO e Windows Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planejar sua validação após a migração de caixa postal e teste**

    Migração de caixa postal é Microsoft orientada; Os administradores não precisam fazer nada, visto que a topologia híbrida de pré-requisito é estabelecida. Microsoft executará a validação necessária e teste para certificar-se de que não é interrompida a migração de caixa postal dos usuários; No entanto, os administradores são incentivados a executar o teste e validação no seu lado.  Consulte [sugeridos para testar o plano e validação de pós-migração para os administradores](#suggested-test-plan-and-post-migration-validation-for-admins) de um plano de teste recomendada. 

    > [!Note]
    > Não há suporte para Lync Server 2010. Se você estiver em uma implantação de servidores 2010, você deve planejar uma atualização de servidor ou considere migrar seus usuários para o Microsoft Teams ou Skype para negócios Online.  

5. **Monitorar o Admin Center de notificação**

    Procure o check-out uma notificação no Centro de notificação de administração com mais detalhes e cronograma com respeito à migração de caixa postal dos usuários. Notificações serão enviadas pelo menos 30 dias antes do período sua migração. 

    > [!Note]
    > Se você recebeu uma notificação com cronograma de migração dos usuários e para adiar sua migração para uma razão comercial essencial, você pode fazer isso pelo contato com o Microsoft Support. Observe que você não é possível adiar sua migração além da data de aposentadoria, fevereiro de 2020. Para clientes que podem ter mais perguntas, contate sua equipe de conta ou o Microsoft Support. Clientes que usam o Office 365 já podem enviar um caso de suporte através do portal de administração do Office 365. 

6. **Considere optando por em iniciando a partir de maio de 2019**

    Você pode aceitar para uma migração de serviço de caixa postal inicial de maio de 2019 (se você não recebeu uma notificação de migração), para alinhar sua migração com um férias de equipe de anuidade ou administrador de licença ou para evitar períodos essenciais aos negócios. Detalhes sobre o processo de consentimento serão atualizadas neste artigo antes de maio de 2019.  

## <a name="appendix"></a>Apêndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de recurso de serviços em nuvem ExchUMO e Windows Azure 




| Serviço do  | Nível de recurso | Recurso | Notas  | Nuvem VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Recursos do serviço| Suporte a PBX de terceiros 3rd    |  | N   | Y    |
| VM | Recursos do serviço  | Suporte Skype para Business Server   |  | Q1CY19 | Y    |
| VM | Recursos do serviço | Suporte para as equipes da Microsoft|  | Y | N    |
| VM | Recursos do serviço | Bloqueio e descoberta eletrônica  | Segurança e conformidade  | S | S    |
| VM | Recursos do serviço | Suporte de regras do Exchange | Segurança e conformidade  | S | S    |
| VM | Recursos de usuário | Acesso de discagem PSTN  | Acesso do assinante  | N | Y    |
| VM | Recursos de usuário | PSTN Outlook Voice Access   | Acesso do assinante  | N | Y    |
| VM | Recursos de usuário | Discada usando um ponto de extremidade autenticado | Chamar o serviço de correio de voz para escutar mensagens de voz e alterar configurações de caixa postal| S | S    |
| VM | Recursos de usuário | Configuração de usuário para desabilitar a caixa postal   |  | S | S    |
| VM | Recursos de usuário | Configuração para alterar a saudação pessoal do usuário  |  | S | S    |
| VM | Recursos de usuário | Configuração para criar uma saudação de ausência temporária do usuário  |  | S | S    |
| VM | Recursos de usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VM | Recursos de usuário | Configuração de substituição de saudação padrão com TTS do usuário  |  | Y | N    |
| VM | Recursos de usuário | Saudações pessoais registros (dispositivo autenticado) |  | S | S    |
| VM | Recursos de usuário | Anote saudações pessoais (PSTN) - tocar no telefone |  | N | Y    |
| VM | Recursos de usuário | Para desabilitar a transcrição da configuração do usuário |  | N | Y    |
| VM | Recursos de usuário | Transcrição  |  | S | S    |
| VM | Recursos de usuário | Caixa postal Visual em todos os pontos de extremidade   | Com o controle de usuário para reproduzir, delete, o indicador de espera de mensagem e alternância de status, em todos os suportados pontos de extremidade  | S | S    |
| VM | Recursos de usuário | Formato de arquivo de áudio MP3 no Outlook    |  | S | S    |
| VM | Recursos de usuário | Controle de reprodução de velocidade variável |  | S | S    |
| VM | Recursos de usuário | Encaminhar uma caixa postal  | Encaminhar uma caixa postal recebido para outros usuários | Y | S    |
| VM | Recursos de usuário | Enviando uma mensagem de voz a um grupo de usuários  |Difusão de caixa postal   | N | Y   |
| VM | Recursos de usuário | Notificação de caixa postal usando o SMS    | Os usuários podem receber um SMS quando possuem um novo correio de voz    | N | Y    |
| VM | Recursos de usuário | Idiomas de saudação com suporte | Detalhes aqui:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | S    |
| VM | Recursos de usuário | Regras de atendimento de chamada |  | Q1CY19 | Y    |
| VM | Recursos de usuário | Tocar no telefone (PSTN) – para reproduzir a mensagem | Ligar para mim na minha célula para ouvir a mensagem de voz  | N | Y    |
| VM | Recursos de usuário | Tocar no telefone (Auth) - reproduzir a mensagem | Ligar para mim no meu dispositivo autenticado  | Y | S    |
| VM | Recursos de usuário | Caixa de correio compartilhada entre vários usuários |  | Y | S    |
| VM | Recursos do chamador  | Experiência do chamador - caixa postal protegida | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegido| N | Y    |
| VM | Recursos do chamador  | Experiência do chamador - caixa postal privada | O chamador pode escolher uma opção para marcar uma mensagem gravada como particular  | N | Y    |
| VM | Recursos do chamador  | Detecção de silêncio   |  | N | Y    |
| VM | Recursos de administração de Inquilino | Nível do servidor de correio de voz protegido    | Administração de inquilino pode configurar uma regra de nível de serviço para marcar a caixa postal de entrada como protegido | Y | S    |
| VM | Recursos de administração de Inquilino | Limite de tempo de duração de gravação de alteração  | Disco rígido CVM codificada como 5 minutos    | N | Y    |
| VM | Recursos de administração de Inquilino | Tempo limite de detecção de silêncio de alteração    |  | N/D    | Y    |
| VM | Recursos de administração de Inquilino | Alterar o número de falha de entrada | CVM: codificados como 3 | N | Y    |
| VM | Recursos de administração de Inquilino | Alterar o idioma padrão |  | Y | S    |
| VM | Recursos de administração de Inquilino | Ativar/desativar a transcrição |  | Y | S    |
| VM | Recursos de administração de Inquilino | Ativar/desativar a notificação de chamada perdida |  | N | Y    |
| VM | Recursos de administração de Inquilino | Ajudar a melhorar a visualização da caixa postal de Microsoft    |  | S | S    |
| VM | Recursos de administração de Inquilino | Personalizar a mensagem de texto para usuários habilitados|  | N/D    | Y    |
| VM | Recursos de administração de Inquilino | Mascaramento de obscenidades transcrição|  | Y | N    |
| VM | Recursos de administração de Inquilino | Política de caixa postal    |   | S | S    |
| VM | Recursos de administração de Inquilino | Administração do portal da Web   |  | CY19   | Y    |
| VM | Recursos de administração de Inquilino | PowerShell   |  | S | S    |
| AA | Recursos do serviço | PBX de terceiros 3rd suporte AA    |  | N | Y    |
| AA | Recursos do serviço | Suporte Skype para Business Server   |  | S | S    |
| AA | Recursos do serviço | Suporte para as equipes da Microsoft|  | Y | N    |
| AA | Recursos do serviço | Discar por nome, da entrada DTMF    |  | S | S    |
| AA | Recursos do serviço | Discar por nome, a entrada de fala  |  | S | S    |
| AA | Recursos do serviço | Suporte a vários idiomas | Detalhes do idioma aqui:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| AA | Recursos do serviço | Transferir para um operador, um usuário ou CQ |  | S | S    |
| AA | Recursos do serviço | Transferir para um número PSTN internamente (RNL DID)  |  | S | S    |
| AA | Recursos do serviço | Transferir para o número PSTN externamente  |  | Q2CY19 | Y    |
| AA | Recursos do serviço | Horário comercial |  | S | S    |
| AA | Recursos do serviço | Opções de menu | Opções de menu do IVR  | S | S    |
| AA | Recursos do serviço | Atribuindo um número PSTN de nuvem para AA |  | Y | N    |
| AA | Recursos do serviço | Atribuindo um número PSTN em prem a AA  |  | S | S    |
| AA | Recursos do serviço | Seleção de usuário personalizada  | Habilitando os chamadores chegar a lista personalizada de usuários da organização| S | S    |
| AA | Recursos do serviço | Fora do horário comercial e feriados tratamento  |  | S | S    |
| AA | Recursos do serviço | Saudação personalizada usando o texto em fala  |  | S | S    |
| AA | Recursos do serviço | Discagem de ramais   | Atingir um usuário discando sua extensão  | CY19   | Y    |
| AA | Recursos do serviço | Caixa de correio para os chamadores AA deixar uma mensagem    |  | CY19   | Y    |
| AA | Recursos do serviço | Atribuição de número de PSTN vários para um AA|  | S | S    |
| AA | Recursos de administração de Inquilino | Administração do portal da Web   |  | Y | N    |
| AA | Recursos de administração de Inquilino | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos do serviço | Integração de fax|  | N | Y    |



### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação de pós-migração para administradores

Ao testar a funcionalidade de caixa postal depois que os usuários foram migrados, verifique se a considerar os seguintes cenários:

- Validar o acesso de caixa postal em todos os tipos de ponto de extremidade em sua organização: telefones IP e aplicativos. 
- Valide com usuários de amostra que o configurado saudações personalizadas são reproduzidas a chamadores.   
- Se sua organização tiver um requisito legal ou de conformidade para desabilitar a transcrição para usuários, verifique se que ele está desabilitado postar a migração. Para obter mais detalhes, consulte [Configure a caixa postal do sistema telefônico](/microsoftteams/set-up-phone-system-voicemail).
- Se você já tiver configurado as regras e políticas de máquina virtual do Exchange, certifique-se de que eles são eficazes.
- Familiarize-se com os cmdlets do PowerShell do serviço de caixa postal de nuvem para alterar as configurações do usuário.  


### <a name="user-experience-impact"></a>Impacto da experiência do usuário

A seguir está uma visão geral da experiência do usuário final voicemail migração.


|Experiência  |Alteração na experiência do usuário|
|---------|---------|
|Notificação por e-mail | Nenhuma alteração<br>Nenhum email é enviada aos usuários notificando sobre ativação/migração de contas de caixa postal. |
|Acesso a mensagens anteriores | Nenhuma alteração<br>Os usuários terão acesso às suas mensagens de caixa postal anterior em todos os pontos de extremidade com suporte. |
|Recebendo VM no outlook, SFB Apps| Nenhuma alteração<br>Usuários continuarão a receber suas mensagens de caixa postal no todos os pontos de extremidade com suporte. |
|Transcrição | Avançado<br>Transcrição CVM tem uma taxa de precisão muito superior e os idiomas com suporte que ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários poderão alterar suas preferências de um Portal de configuração do usuário (USP). Os usuários podem acessar seu USP a partir de um hiperlink em seus emails de caixa postal ou no botão Configurações de usuário em seu cliente SFB; https://aka.ms/vmsettings.   
 |Recursos| Consulte a comparação de conjunto de recursos para obter detalhes. |
|Regras do Outlook para mensagens VM | Nenhuma alteração<br>Anteriormente criadas regras serão aplicadas a mensagens CVM após a migração.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento de usuário e provisionamento em CVM 

Skype para novos usuários de negócios será provisionada automaticamente para a caixa postal no serviço CVM quando criado. Nenhum trabalho adicional admin ou a licença é necessária para provisionar novos usuários para caixa postal. Consulte [Configure a caixa postal do sistema telefônico](/microsoftteams/set-up-phone-system-voicemail) para saber mais sobre como gerenciar as políticas para usuários novos e existentes.

#### <a name="admin-auto-attendant-management-experience"></a>Experiência de gerenciamento de atendedor automático de Admin 

Consulte [Set up um atendedor automático de sistema telefônico](../../SfbOnline/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md) para saber mais sobre como configurar e gerenciar os atendedores automáticos. 
