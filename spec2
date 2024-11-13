import React from 'react';
import { HashRouter } from 'react-router-dom';
import { render, fireEvent, waitFor, screen } from '@testing-library/react';
import '@testing-library/jest-dom';
import { Provider } from 'react-redux';
import { Select, TextField } from 'uds-core';
import ATPFormPage from '../atpFormPage';
import { mockStore, renderWithNoSVGs } from '../../../../test/helpers';
import { KEY } from '../../../reducers';
import { devProps } from '../../../utils/constant';
import { Col } from '../../../style/form.styles';

jest.mock('react-i18next', () => ({
  useTranslation: () => {
    return {
      t: (str) => str,
    };
  },
}));

describe('ATPForm Page', () => {
  const props = {
    apiConfiguration: devProps.apiConfiguration,
    setData: jest.fn(),
    ATPFlags: {
      ATPFormPageFlags: {
        isDebt: true,
        isTotalFX: true,
        ispurposeEnable: true,
        ispaymenttypes: true,
        issecuritytypes: true,
        isEnablePrincipalCol: true,
        isSpecify: true,
        isSpecifyTooltip: true,
      }
    },

    purposeCategories: {
      purposeCategories: [
        {
          'id': 20883,
          'name': 'Foreign loans /borrowings'
        },
        {
          'id': 20884,
          'name': 'Inward Investments by Non-Residents'
        },
        {
          'id': 20885,
          'name': 'Outward Investments by Residents'
        },
        {
          'id': 20886,
          'name': 'Trade (payment for importations)'
        },
        {
          'id': 20887,
          'name': 'Resident to resident transactions'
        },
        {
          'id': 20888,
          'name': 'Non-trade current account transactions'
        },
        {
          'id': 20889,
          'name': 'Others'
        },

      ],
      purposes: [
        {
          'id': 20892,
          'categoryId': 20884,
          'name': 'Repatriation of capital',
          'type': 'PURPOSE'
        },
        {
          'id': 20893,
          'categoryId': 20884,
          'name': 'Remittance of earnings',
          'type': 'PURPOSE'
        },
        {
          'id': 20894,
          'categoryId': 20884,
          'name': 'Remittance in equivalent FX of excess pesos (funded by inward remittance of FX) from unrealized investments in the Philippines',
          'type': 'PURPOSE'
        },
        {
          'id': 20895,
          'categoryId': 20884,
          'name': 'Settlement of FX obligations/payables of residents to non-resident investors relative to FX-denominated' +
            ' equity and debt securities issued by residents that are not partaking the nature of a foreign loan',
          'type': 'PURPOSE'
        },
        {
          'id': 20896,
          'categoryId': 20884,
          'name': 'Remittance in equivalent FX of peso proceeds from onshore sale by non-resident issuers of their equity and debt securities',
          'type': 'PURPOSE'
        },
        {
          'id': 20897,
          'categoryId': 20885,
          'name': 'Equity securities',
          'type': 'PURPOSE'
        },
        {
          'id': 20898,
          'categoryId': 20885,
          'name': 'Debt securities',
          'type': 'PURPOSE'
        },
        {
          'id': 20899,
          'categoryId': 20885,
          'name': 'Offshore Mutual Funds (MFs)/Unit Investment Trust Funds (UITFs)',
          'type': 'PURPOSE'
        },
        {
          'id': 20900,
          'categoryId': 20885,
          'name': 'Intercompany loan between/among related parties',
          'type': 'PURPOSE'
        },
        {
          'id': 20901,
          'categoryId': 20885,
          'name': 'Purchase of real property abroad, such as condominium units and those for/under construction',
          'type': 'PURPOSE'
        },
        {
          'id': 20902,
          'categoryId': 20885,
          'name': 'Instruments issued onshore by non-residents requiring settlement in foreign currency',
          'type': 'PURPOSE'
        },
        {
          'id': 20903,
          'categoryId': 20885,
          'name': 'Others',
          'type': 'PURPOSE'
        },
        {
          'id': 20934,
          'categoryId': 20885,
          'name': 'Total FX purchases for the current calendar year',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20904,
          'categoryId': 20887,
          'name': 'Obligations to residents',
          'type': 'PURPOSE'
        },
        {
          'id': 20905,
          'categoryId': 20887,
          'name': 'Investments in instruments (including time deposits with at least 90-day maturity with onshore' +
            ' banks but excluding other bank deposits such as savings and demand) that are issued by other residents',
          'type': 'PURPOSE'
        },
        {
          'id': 20906,
          'categoryId': 20887,
          'name': 'Foreign currency loans owed to banks operating in the Philippines (FCDU/EFCDU/RBU)',
          'type': 'PURPOSE'
        },
        {
          'id': 20907,
          'categoryId': 20887,
          'name': 'Others',
          'type': 'PURPOSE'
        },
        {
          'id': 20908,
          'categoryId': 20888,
          'name': 'Services',
          'type': 'PURPOSE'
        },
        {
          'id': 20909,
          'categoryId': 20888,
          'name': 'Non-merchandise Insurance',
          'type': 'PURPOSE'
        },
        {
          'id': 20910,
          'categoryId': 20888,
          'name': 'Travel Expenses',
          'type': 'PURPOSE'
        },
        {
          'id': 20911,
          'categoryId': 20888,
          'name': 'Commissions',
          'type': 'PURPOSE'
        },
        {
          'id': 20912,
          'categoryId': 20888,
          'name': 'Professional/Management Fees',
          'type': 'PURPOSE'
        },
        {
          'id': 20913,
          'categoryId': 20888,
          'name': 'Royalties',
          'type': 'PURPOSE'
        },
        {
          'id': 20914,
          'categoryId': 20888,
          'name': 'Income',
          'type': 'PURPOSE'
        },
        {
          'id': 20915,
          'categoryId': 20888,
          'name': 'Refund of unused grants/donations',
          'type': 'PURPOSE'
        },
        {
          'id': 20916,
          'categoryId': 20888,
          'name': 'Others',
          'type': 'PURPOSE'
        },
        {
          'id': 20917,
          'categoryId': 20889,
          'name': 'Conversion to FX of peso deposit accounts of non-residents',
          'type': 'PURPOSE'
        },
        {
          'id': 20918,
          'categoryId': 20889,
          'name': 'Others',
          'type': 'PURPOSE'
        },
        {
          'id': 20890,
          'categoryId': 20883,
          'name': 'Owed to Non-residents (other than OBUs)',
          'type': 'PURPOSE'
        },
        {
          'id': 20891,
          'categoryId': 20883,
          'name': 'Owed to Offshore Banking Units in the Philippines',
          'type': 'PURPOSE'
        },
        {
          'id': 20933,
          'categoryId': 20883,
          'name': 'Debt Account No',
          'type': 'ADDL_PURPOSE_DET'
        }
      ],
      payments: [
        {
          'id': 20925,
          'purposeId': 20897,
          'name': 'not listed at an exchange',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20926,
          'purposeId': 20897,
          'name': 'listed at an exchange',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20935,
          'purposeId': 20903,
          'name': '(Please specify)',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20936,
          'purposeId': 20905,
          'name': '(Please specify)',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20921,
          'purposeId': 20906,
          'name': 'Prepayment',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20922,
          'purposeId': 20906,
          'name': 'Regular Payment',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20937,
          'purposeId': 20907,
          'name': '(Please specify)',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20938,
          'purposeId': 20908,
          'name': '(Please specify)',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20923,
          'purposeId': 20909,
          'name': 'Premium',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20924,
          'purposeId': 20909,
          'name': 'Claims/payables',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20939,
          'purposeId': 20916,
          'name': '(Please specify)',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20940,
          'purposeId': 20918,
          'name': '(Please specify)',
          'type': 'ADDL_PURPOSE_DET'
        },
        {
          'id': 20919,
          'purposeId': 20891,
          'name': 'Prepayment',
          'type': 'PAYMENT_TYPE'
        },
        {
          'id': 20920,
          'purposeId': 20891,
          'name': 'Regular Payment',
          'type': 'PAYMENT_TYPE'
        }
      ],
      paymentComponents: [
        {
          'id': 20930,
          'name': 'Principal',
          'paymentId': 20922
        },
        {
          'id': 20931,
          'name': 'Interest',
          'paymentId': 20922
        },
        {
          'id': 20932,
          'name': 'Fee',
          'paymentId': 20922
        },
        {
          'id': 20927,
          'name': 'Principal',
          'paymentId': 20920
        },
        {
          'id': 20928,
          'name': 'Interest',
          'paymentId': 20920
        },
        {
          'id': 20929,
          'name': 'Fee',
          'paymentId': 20920
        }
      ]
    },
    formFieldErrorIds: [
      'purposeCategory',
      'totalFXPurchased',
      'debtAccount',
      'purpose',
      'paymentType',
      'securityType',
      'specifiedReason',
      'specifiedReason',
      'principal',
      'interest',
      'fees',
    ],
    formDetails: {
      purpose: {
        purposeCategory: 'Outward Investments by Residents',
        totalFXPurchased: '',
        debtAccount: '',
        purpose: '',
        paymentType: '',
        securityType: '',
        othersReason: ''
      },
      purposeData: [
        {
          'id': 20891, 'categoryId': 20883,
          'name': 'Owed to Offshore Banking Units in the Philippines',
          'type': 'PURPOSE'
        },
      ],
      paymentTypesData: [
        {
          'id': 20919, 'purposeId': 20891,
          'name': 'Prepayment', 'type': 'PAYMENT_TYPE'
        },
      ],
      securityTypesData: [],
    },
  };

  const state = {
    [KEY]: {
      tradeReducer: {
        purposeCategories: {
          purposeCategories: [
            {
              'id': 20505,
              'name': 'Foreign loans /borrowings'
            }
          ],
          purposes: [
            {
              'id': 20512,
              'categoryId': 20505,
              'name': 'Owed to Non-residents (other than./ OBUs)',
              'type': 'PURPOSE'
            },
          ],
          payments: [
            {
              'id': 20541,
              'purposeId': 20513,
              'name': 'Prepayment',
              'type': 'PAYMENT_TYPE'
            }
          ],
          paymentComponents: [
            {
              'principal': 'Principal',
              'interest': 'Interest',
              'fees': 'Fee',
              'paymentId': 20542
            },
            {
              'principal': 'Principal',
              'interest': 'Interest',
              'fees': 'Fee',
              'paymentId': 20544
            }
          ]
        }
      },
    },
  };

  test('ATPForm Purpose Section', async () => {
    const wrapper = renderWithNoSVGs(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    expect(wrapper).toMatchSnapshot();
  });

  let mockTrade;
  beforeEach(() => {
    mockTrade = jest.fn();
    jest.clearAllMocks();
  });

  it('Purpose Category Component', async () => {
    const mockResult = {};
    mockTrade.mockResolvedValue(mockResult);
    const wrapper = renderWithNoSVGs(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    expect(wrapper).toMatchSnapshot();
    fireEvent.click(wrapper.container.querySelector('[data-testid="input"]'));
  });

  it('Purpose Category onchange event Handler', async () => {
    const { container, getAllByTestId, rerender } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[0]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    await waitFor(() => expect(container.querySelector('[data-testid="purpose"]')).toBeInTheDocument());
  });

  it('Foreign loans /borrowings Purpose  onchange event Handler', async () => {
    const { container, getAllByTestId, rerender } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[0]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[6]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    expect(container.querySelector('[data-testid="purpose"]')).toBeInTheDocument();
  });

  it('Outward Investments by Residents Purpose  onchange event Handler', async () => {
    const { container, getAllByTestId, rerender } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[0]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[1]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    expect(container.querySelector('[data-testid="purpose"]')).toBeInTheDocument();
  });

  it('Trade (payment for importations) Purpose  onchange event Handler', async () => {
    const { container, getAllByTestId, rerender } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[0]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[2]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...props} />
        </Provider>
      </HashRouter>
    );
    expect(container.querySelector('[data-testid="input-root"]')).toBeInTheDocument();
  });

  it('should match snapshot test', () => {
    const { container } = render(
      <TextField
        placeholder="Email Address"
        helperText="Please Enter valid Email"
      />
    );
    expect(container).toMatchSnapshot();
  });

  test('Should handle suggestionHandler', () => {
    const suggestionHandler = jest.fn();
    const selectedHandler = jest.fn();
    const options = [{
      'id': 20884,
      'name': 'Inward Investments by Non-Residents'
    },
    {
      'id': 20885,
      'name': 'Outward Investments by Residents'
    }];

    const wrapper = render(
      <Col>
        <Select
          suggestions={options}
          handleSelectedSuggestion={selectedHandler}
          handleSuggestions={suggestionHandler}
          icon={{ position: 'right', iconName: 'ic_chevron_down_blue' }}
          isFocusOpen
          isFilterDropdown
          title={{ label: 'Purpose Category' }}
          placeholder="Select"
        />
      </Col>
    );
    fireEvent.click(wrapper.container.querySelector('[data-testid="input-root"]'));
    expect(wrapper).toMatchSnapshot();
  });

  it('onchange event Handler for inputs', async () => {
    const purposeprops = {
      ...props,
      ATPFlags: {
        ATPFormPageFlags: {
          ...props?.ATPFlags?.ATPFormPageFlags,
          isSpecify: true, isSpecifyTooltip: false,
        },
      }
    };
    const { getAllByTestId } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    fireEvent.change(getAllByTestId('input')[0], { target: { value: 'Test' } });
    fireEvent.change(getAllByTestId('input')[1], { target: { value: 'Test Address' } });
    fireEvent.change(getAllByTestId('input')[2], { target: { value: 'Test Address' } });
    fireEvent.change(getAllByTestId('input')[3], { target: { value: 'Test Address' } });
    fireEvent.change(getAllByTestId('input')[4], { target: { value: 'Test Address' } });
  });

  it('purposeselectedHandler  onchange event Handler', async () => {
    const purposeprops = {
      ...props,
      ATPFlags: {
        ATPFormPageFlags: {
          isDebt: true, isTotalFX: false, ispurposeEnable: true, ispaymenttypes: true,
          issecuritytypes: false, isEnablePrincipalCol: false, isSpecify: false, isSpecifyTooltip: false,
        },
      },
      formDetails: {
        ...props.formDetails,
        purposeData: [
          {
            'id': 20891, 'categoryId': 20883,
            'name': 'Owed to Offshore Banking Units in the Philippines', 'type': 'PURPOSE'
          },
        ],
        paymentTypesData: [
          {
            'id': 20919, 'purposeId': 20891,
            'name': 'Prepayment', 'type': 'PAYMENT_TYPE'
          },
        ]
      },
      ATPFormDetails: {
        debtAccount: 'test', fees: '', interest: '', paymentType: 'Prepayment',
        principle: '', purpose: 'Owed to Offshore Banking Units in the Philippines',
        purposeCategory: 'Foreign loans /borrowings', securityType: '',
        specifiedReason: '', totalFXPurchased: '',
      },

      purposeCategories: {
        ...props.purposeCategories,
        purposeCategories: [
          {
            'id': 20883,
            'name': 'Foreign loans /borrowings'
          }
        ],
        purposes: [
          {
            'id': 20891, 'categoryId': 20883,
            'name': 'Owed to Offshore Banking Units in the Philippines', 'type': 'PURPOSE'
          },
        ],
        payments: [
          {
            'id': 20919, 'purposeId': 20891,
            'name': 'Prepayment', 'type': 'PAYMENT_TYPE'
          },
        ]
      }
    };
    const { container, getAllByTestId, rerender } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[0]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[2]);
    screen.debug();
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    expect(container.querySelector('[data-testid="paymentTypes"]')).toBeInTheDocument();
    // fireEvent.focus(getAllByTestId('input')[3]);
    // screen.debug();
    // fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
  });
  it('securityTypesselectedHandler  onchange event Handler', async () => {
    const purposeprops = {
      ...props,
      ATPFlags: {
        ATPFormPageFlags: {
          isDebt: true, isTotalFX: false, ispurposeEnable: true, ispaymenttypes: false,
          issecuritytypes: true, isEnablePrincipalCol: false, isSpecify: false, isSpecifyTooltip: false,
        },
      },

      ATPFormDetails: {
        debtAccount: 'test', fees: '', interest: '', paymentType: '', principle: '', purpose: 'Equity securities',
        purposeCategory: 'Outward Investments by Residents',
        securityType: 'not listed at an exchange', specifiedReason: '', totalFXPurchased: '',
      },

      purposeCategories: {
        ...props.purposeCategories,
        purposeCategories: [
          {
            'id': 20885,
            'name': 'Outward Investments by Residents'
          },
        ],
        purposes: [
          {
            'id': 20897, 'categoryId': 20885,
            'name': 'Equity securities', 'type': 'PURPOSE'
          },
        ],
        payments: [
          {
            'id': 20925, 'purposeId': 20897,
            'name': 'not listed at an exchange', 'type': 'SECURITY_TYPE'
          },
        ]
      }
    };
    const { container, getAllByTestId, rerender } = render(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    fireEvent.focus(getAllByTestId('input')[0]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    expect(container.querySelector('[data-testid="purpose"]')).toBeInTheDocument();
    fireEvent.focus(getAllByTestId('input')[2]);
    fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
    rerender(
      <HashRouter>
        <Provider store={mockStore(state)}>
          <ATPFormPage {...purposeprops} />
        </Provider>
      </HashRouter>
    );
    expect(container.querySelector('[data-testid="securityTypes"]')).toBeInTheDocument();
    fireEvent.focus(getAllByTestId('input')[3]);
    // fireEvent.mouseDown(container.querySelectorAll('[name="test_menuitem"]')[0]);
  });
});
