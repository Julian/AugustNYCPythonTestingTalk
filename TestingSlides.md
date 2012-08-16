# Testing Tools
## Julian Berman

---

# Testing

> What

> How

> **Why**

---

# Discovery

    loader = unittest.TestLoader()
    suite = loader.loadTestsFromTestCase(TestSequenceFunctions)
    unittest.TextTestRunner(verbosity=2).run(suite)

---

# Test Running

- `py.test`
- `trial`
- `nosetests`
- `python -m unittest discover`

---

# Features

- Make explicitly selecting tests easy

> `test foo.bar.TestCase.test_method`

---

# Features

- Fast
- Customizable output
- Test timing

---

# The Opinionated Part

---

## tox
http://tox.testrun.org

---

## coverage.py

- Run tests
- See what ran
- Fix your code
- Write more tests

---

## coverage.py

    class CalculatorTest(unittest.TestCase):
        def setUp(self):
          self.calc = Calculator()


          def test_add(self):
            result = self.calc.add(5, 3)
            self.assertEqual(result, 8)


        def test_subtract(self):
            result = self.calc.subtract(10, 4)
            self.assertEqual(result, 6)


        def multiply_test(self):
            result = self.calc.multiply(9, 2)
            self.assertEqual(result, 18)


        def test_divide(self):
            result = self.calc.divide(6, 3)
            self.assertEqual(result, 2)

            with self.assertRaises(ZeroDivisionError):
                self.calc.divide(10, 0)
                self.calc.divide(0, 0)


[Coverage](../htmlcov/index.html)

---

## mock

    import mock
    import foundausefortwitter as fauft

    def test_twitter(self):
        with mock.patch("fauft.urlopen", return_value=my_html) as m:
            messages = self.twitter_scraper.fetch(user="@NYCPython")
            self.assertTrue(m.called)
            self.assertEqual(messages, ["Hello", "World"])

---

## Debuggers

- `pdb`
- `pdb++`
- `pudb`

---

## pdb++

![pdb++](../pdbpp.png)

---

## ` Your Editor Here `

- tslime
- AsyncMakeGreen
- ViMux

---

> Questions
