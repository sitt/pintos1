Changes made to the following to build the test:

*under ..src/tests/threads/ created a new file alarm-mega.ck similar to alarm-multiple.ck but change the parameter to 70

*edited the file alarm-wait.c added a function test_alarm_mega : 

void
test_alarm_mega (void)
{
  test_sleep( 5, 70);
}

*edited the file test.c to include alarm-mega test case:

static const struct test tests[] = 
  {
    {"alarm-single", test_alarm_single},
    {"alarm-multiple", test_alarm_multiple},
    {"alarm-mega", test_alarm_mega},
  .....
  ....
  }

*edited the file tests.h to include the extern:

extern test_func test_alarm_mega;

*edited the file Rubric.alarm to include the following line:

4       alarm-mega

*under ..src/threads/

executed  make clean, make
