No Microsoft Teams, uma conta de recurso é necessária para cada atendente automático ou fila de chamadas. Contas de recurso também podem ser atribuídas números de telefone de serviço. É assim que você atribui números de telefone a atendentes automáticos e filas de chamadas permitindo que os chamadores de fora do Teams cheguem à fila de atendimento automático ou de chamada.

Este artigo aborda como criar contas de recursos e prepará-las para uso com atendentes automáticos e filas de chamadas.

Antes de iniciar os procedimentos neste artigo, verifique se você fez o seguinte:

- [Obter licenças da Conta de Recursos Telefonia do Microsoft Teams](#obtain-microsoft-teams-phone-resource-account-licenses)
- [Obter números de serviço](#obtain-service-numbers)

> [!NOTE]
> As contas de recurso usadas para atendentes automáticos e filas de chamadas estão desabilitadas para entrar e devem permanecer assim. Chat e presença não estão disponíveis para essas contas.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Obter licenças da Conta de Recursos Telefonia do Microsoft Teams

Cada conta de recurso requer uma licença para trabalhar com atendentes automáticos e filas de chamadas, conhecidas como uma *licença Telefonia do Microsoft Teams Conta de Recursos*. As assinaturas com o Teams Phone obtêm automaticamente uma alocação gratuita de *licenças Telefonia do Microsoft Teams Conta de Recursos* e, se mais forem necessárias, mais Telefonia do Microsoft Teams licenças da *Conta de Recursos* podem ser adquiridas. Para obter detalhes sobre como obter essas licenças, consulte [Telefonia do Microsoft Teams licenças da Conta de Recursos](../teams-add-on-licensing/virtual-user.md).

Abordamos como [atribuir a licença a uma conta de recurso mais adiante neste artigo](#assign-a-license).

Se você comprou **Telefonia do Teams Padrão** ou **o Teams Phone com** licenças de pacote de plano de chamada, as licenças *da Conta de Recursos do Teams Phone* já estão em sua conta.

Para ver se você já tem licenças da Conta de Recursos, faça logon no Microsoft 365 usando uma conta com permissões de administrador global. Em seguida, vá para [Cobrança > Seus produtos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se você tiver licenças da Conta de Recursos, elas aparecerão como **Telefonia do Microsoft Teams Conta de Recursos**.

1. Abra o Centro de administração do Microsoft 365 e faça logon com um usuário que é um administrador global. Geralmente, essa é a conta usada para se inscrever no Microsoft 365.
2. No painel de navegação à esquerda, acesse [**Complementos** de **Serviços** de Compra de Cobrança  > ](https://admin.microsoft.com/Adminportal/Home#/catalog)**Consulte todos os produtos de complementos**. >  > 
3. Role até o final para encontrar a licença **Telefonia do Microsoft Teams Conta de Recursos**. Selecione **Detalhes** e **compre**.
4. Na página de compra de licença, selecione o número de licenças da Conta de Recurso desejada. Você precisa de uma licença de Conta de Recurso para cada atendente automático e fila de chamadas que planeja configurar. Recomendamos selecionar pelo menos cinco licenças para que você possa configurar facilmente mais atendentes automáticos e filas de chamadas no futuro sem precisar comprar mais licenças imediatamente.
5. Desmarque **a atribuição automática a todos os usuários sem licenças**.
6. Selecione **Verificar agora**.
7. Confirme seu pedido, selecione **Avançar** e, em seguida, **Faça o pedido**.

Há um custo zero, mas você ainda precisa seguir essas etapas para adquirir a licença.

### <a name="obtain-service-numbers"></a>Obter números de serviço

Os números de serviço são opcionais para atendentes automáticos e filas de chamadas, no entanto, você precisará de pelo menos um número de serviço para que os chamadores cheguem à configuração de fila de atendimento automático e de chamada. Para qualquer atendente automático ou fila de chamadas que você deseja ser acessível diretamente por um número de serviço, você deve ter uma conta de recurso com um número de serviço associado.

As contas de recurso podem usar números de serviço gratuitos ou de pedágio. Você pode solicitar novos números ou portar números existentes de outra operadora.

Para obter novos números de serviço, consulte [Obtendo números de telefone de serviço](../getting-service-phone-numbers.md).

Para portar um número de outra operadora, consulte [Transferir números de telefone para o Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no centro de administração do Teams.

1. No centro de administração do Teams, expanda **Voz** e selecione **Contas de recursos**.
2. Selecione **Adicionar**.
3. No painel **Adicionar conta de recurso** , preencha **Nome de exibição**, **Nome de usuário** e o **tipo de conta de recurso**. O tipo de conta de recurso pode ser **o atendente automático** ou **a fila de chamadas**, dependendo de como você pretende usar essa conta de recurso.
4. Selecione **Salvar**.

## <a name="assign-a-license"></a>Atribuir uma licença

Para cada conta de recurso, você deve atribuir uma licença *Telefonia do Microsoft Teams Conta de Recurso* ou *Telefonia do Teams Padrão* licença.

1. No Centro de administração do Microsoft 365, expanda **Usuários** e selecione **Usuários ativos**.
2. Selecione a conta de recurso à qual você deseja atribuir uma licença. O painel de usuário da conta de recurso será exibido.
3. Na guia **Licenças e Aplicativos**, em **Licenças**, selecione **Telefonia do Microsoft Teams Conta de Recursos**.
4. Selecione **Salvar alterações**.

## <a name="assign-a-service-number"></a>Atribuir um número de serviço

Se você estiver planejando usar a conta de recurso com um atendente automático ou uma fila de chamadas que requer um número de serviço, atribua um número à conta de recursos.

1. No centro de administração do Teams, na página **Contas de recurso** , selecione a conta de recurso à qual você deseja atribuir um número de serviço e **selecione Atribuir/não atribuir**.
2. Na lista suspensa **Tipo de número** de telefone, escolha o tipo de número que você deseja usar.
3. Na caixa **Número de telefone atribuído** , pesquise o número que você deseja usar e selecione **Adicionar**. Certifique-se de incluir o código do país (por exemplo, +1 250 555 0012).
4. Selecione **Salvar**.

Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisa usar o PowerShell:

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`
